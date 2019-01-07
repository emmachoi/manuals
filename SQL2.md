- [SQL Reference](#sql-reference)
  - [3.데이터 정의어](#3%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%95%EC%9D%98%EC%96%B4)
  - 



### CREATE TABLE

#### 구문

**create_table ::=**

![CREATE_TABLE_2](media/SQL/CREATE_TABLE_2.gif)

[table_constraint
::=](#table_constraint), [temporary_attributes_clause
::=](#temporary_attributes_clause),
[table_partitioning_clause](#table_partitioning_clause), [access_mode_clause
::=](#access_mode_clause_CREATETALBE), [physical_attributes_clause
::=](#create_table_physical_attributes_clause), [log_compression_clause
::=](#log_compression_clause), [logging_clause ::=](#logging_clause),
[parallel_clause::=](#parallel_clause), [table_compression_clause
::=](#table_compression_clause), [lob_column_properties
::=](#lob_column_properties)

**column_definition ::=**

![column_definition_image113](media/SQL/column_definition_image113.gif)

**encrypt_clause::=**

![encrypt_clause](media/SQL/encrypt_clause.gif)

**variable_clause::=**

![variable_clause](media/SQL/variable_clause.gif)

**in_row_clause::=**

![in_row_clause](media/SQL/in_row_clause.gif)

**default_clause::=**

![default_clause](media/SQL/default_clause.gif)

**column_constraint ::=**

![column_constraint_image114](media/SQL/column_constraint_image114.gif)

**unique_clause ::=**

![unique_clause](media/SQL/unique_clause.gif)

**unique_specification ::=**



![unique_specification](media/SQL/unique_specification.gif)





**sort_order_clause ::=**

![sort_order_clause](media/SQL/sort_order_clause.gif)

**directkey_clause ::=**

![directkey_clause](media/SQL/directkey_clause.gif)

**using_index_clause ::=**

![using_index_clause_image117](media/SQL/using_index_clause_image117.gif)

**index_attribute_clause ::=**

![index_attribute_clause_image118](media/SQL/index_attribute_clause_image118.gif)

[memory_index_attributes ::=](#memory_index_attributes), [disk_index_attributes
::=](#disk_index_attributes)

**references_clause::=**

![references_clause](media/SQL/references_clause.gif)

**check_clause ::=**

![check_clause](media/SQL/check_clause.gif)

<a name="table_constraint"><a/>

**table_constraint ::=**

![table_constraint](media/SQL/table_constraint.gif)

**table_unique_clause ::=**

![table_unique_clause](media/SQL/table_unique_clause.gif)

**referential_constraint ::=**

![referential_constraint](media/SQL/referential_constraint.gif)

[references_clause ::=](#references_clause)

<a name="temporary_attributes_clause"><a/>

**temporary_attributes_clause ::=**

![temporary_attributes_clause](media/SQL/temporary_attributes_clause.gif)



<a name="table_partitioning_clause"><a/>

**table_partitioning_clause ::=**

![table_partitioning_clause_image123](media/SQL/table_partitioning_clause_image123.gif)

**range_partitioning ::=**

![range_partitioning_image124](media/SQL/range_partitioning_image124.gif)

**partition_default_clause ::=**

![partition_default](media/SQL/partition_default.gif)

<a name="table_partition_description"><a/>

**table_partition_description ::=**

![TABLE_PARTITION_DESCRIPTION_2](media/SQL/TABLE_PARTITION_DESCRIPTION_2.gif)

[lob_column_properties ::=](#lob_column_properties)*,* [access_mode_clause
::=](#access_mode_clause_CREATETALBE)

**partition_range_clause ::=**

![partition_range_clause_image126](media/SQL/partition_range_clause_image126.gif)

[table_partition_description ::=](#table_partition_description)



**hash_partitioning ::=**

![hash_paritioning_image126_1](media/SQL/hash_paritioning_image126_1.gif)

[table_partition_description ::=](#table_partition_description)





**list_partitioning ::=**

![list_partitioning_image127](media/SQL/list_partitioning_image127.gif)

[partition_default_clause ::=](#partition_default_clause)

**partition_list_clause ::=**



![table_list_clause_image128](media/SQL/table_list_clause_image128.gif)



<a name="row_movement_clause"><a/>

**row_movement_clause ::=**

![row_movement_clause](media/SQL/row_movement_clause.gif)



<a name="access_mode_clause_CREATETALBE)"><a/>

**access_mode_clause ::=**

![ACCESS_MODE_CLAUSE_](media/SQL/ACCESS_MODE_CLAUSE_.gif)

<a name="tablespace_clause"><a/>

**tablespace_clause ::=**

![tablespace_clause](media/SQL/tablespace_clause.gif)

<a name="physical_attributes_clause"><a/>

<a name="create_table_physical_attributes_clause"><a/>

**physical_attributes_clause ::=**

![physical_attributes_clause_image130_1](media/SQL/physical_attributes_clause_image130_1.gif)

**storage_clause ::=**

![storage_clause](media/SQL/storage_clause.gif)

<a name="log_compression_clause"><a/>

**log_compression_clause ::=**

![log_compression_clause_image130_2](media/SQL/log_compression_clause_image130_2.gif)



<a name="logging_clause"><a/>

**logging_clause ::=**

![logging_clause](media/SQL/logging_clause.gif)

<a name="parallel_clause"><a/>

**parallel_clause::=**

![PARALLEL_CLAUSE](media/SQL/PARALLEL_CLAUSE.gif)

<a name="table_compression_clause"><a/>

**table_compression_clause ::=**

![table_compression](media/SQL/table_compression.gif)

<a name="lob_column_properties"><a/>

**lob_column_properties ::=**

![lob_column_properties_image133](media/SQL/lob_column_properties_image133.gif)

**LOB_storage_clause ::=**

![lob_storage_clause_image134](media/SQL/lob_storage_clause_image134.gif)

**lob_attributes ::=**

![lob_attribute](media/SQL/lob_attribute.gif)

#### 전제 조건

아래의 조건 중 하나 이상을 만족해야 한다.

- SYS 사용자이다.
- 사용자 자신의 스키마에 테이블을 생성하려면 CREATE TABLE 또는 CREATE ANY
  TABLE 시스템 권한을 가지고 있어야 한다.
- 다른 사용자의 스키마에 테이블을 생성하려면 CREATE ANY TABLE 시스템 권한을
  가지고 있어야 한다.

#### 설명

명시된 이름의 새로운 테이블을 생성한다.

*[GLOBAL] TEMPORARY*

[GLOBAL] TEMPORARY는 테이블이 임시 테이블임을 지정한다. GLOBAL 지정 여부에 따른
차이점은 없으므로 생략해도 된다. 이렇게 생성된 테이블의 정의는 모든 세션에서 볼
수 있지만, 임시 테이블의 데이터는 해당 테이블에 데이터를 삽입하는 세션에서만 볼
수 있다.

사용자가 처음으로 임시 테이블을 만들면, 테이블의 메타 데이터만 데이터 딕셔너리에
저장되고, 테이블의 데이터를 위한 공간은 할당되지 않는다. 해당 테이블에 처음으로
DML 작업이 수행되는 순간에 테이블 세그먼트를 위한 공간이 할당된다. 임시 테이블의
정의는 일반적인 테이블의 정의와 마찬가지로 데이터베이스에서 지속되지만, 임시
테이블의 테이블 세그먼트와 임시 테이블에 저장된 모든 데이터는 세션 또는
트랜잭션에 한정된다. ON COMMIT 키워드를 사용해서 테이블 세그먼트와 데이터가 세션
레벨인지 또는 트랜잭션 레벨인지를 지정할 수 있다. 자세한 설명은 아래의
*temporary_attributes_clause*를 참고하라.

세션에 한정되는 임시 테이블은 세션이 임시 테이블에 바인딩 되지 않은 경우에만
해당 임시 테이블에 대해 DDL 작업(ALTER TABLE, DROP TABLE, CREATE INDEX 등)이
허용된다.

트랜잭션에 한정되는 임시 테이블은 바인딩 여부에 상관 없이 임시 테이블에 대한 DDL
작업이 허용된다. 하지만, Altibase 내부적으로 DDL 작업 수행 전에 커밋을 먼저 하기
때문에, 임시 테이블에 대한 DDL 수행 후에 그 테이블의 데이터는 사라진다.

- 임시 테이블의 제약 사항:
  - 임시 테이블은 파티셔닝이 불가능하다.
  - 임시 테이블에는 외래 키를 지정할 수 없다.
  - lob_storage_clause의 TABLESPACE에는 임시 테이블을 저장하는 휘발성
    테이블스페이스만 올 수 있다.
  - 임시 테이블은 휘발성 테이블스페이스만 저장할 수 있다.
  - 임시 테이블에 대해서는 분산 트랜잭션이 지원되지 않는다.

*user_name*

생성될 테이블 소유자 이름을 명시한다. 생략하면 Altibase는 현재 세션에 연결된
사용자의 스키마에 테이블을 생성한다.

*tbl_name*

생성될 테이블 이름을 명시한다. 테이블 이름은  2장 "객체 이름 규칙"을 따라야 한다.

*column_definition*

- DEFAULT  
  칼럼에 DEFAULT 절을 명시하지 않고 테이블을 생성한 경우, 데이터 삽입시 해당
  칼럼의 값을 명시하지 않으면 NULL이 입력된다.
- TIMESTAMP  
  TIMESTAMP 칼럼은 여러 면에서 다른 데이터 타입들처럼 다뤄진다. 예를 들어,
  CREATE TABLE 문에 칼럼의 데이터 타입으로 TIMESTAMP를 명시한 경우 내부적으로
  데이터 크기가 8Byte인 TIMESTAMP 칼럼이 생성된다. 그러나 TIMESTAMP 칼럼의
  값은 시스템에 의해 결정되기 때문에 명시적으로 DEFAULT 값을 설정할 수 없다.
  또한 TIMESTAMP 칼럼은 한 테이블에 하나만 생성할 수 있다.

*column_constraint*

새로운 테이블을 생성할 때 칼럼에 대한 제약조건을 설정한다. 명시적으로 제약조건의
이름을 지정할 수 있다. LOCALUNIQUE 제약조건은 파티션드 테이블에 사용될 수 있다.

- PRIMARY KEY

  기본키의 값은 테이블 내에서 유일해야 하며 기본키에 속하는 칼럼은 널(NULL) 값을
  가질 수 없다. 한 테이블 내에 정의 가능한 기본키의 개수는 하나이며, 최대 32개
  칼럼들의 조합에 대해 기본 키를 생성할 수 있다.

- UNIQUE

  UNIQUE 제약조건을 정의하면 유니크 키에 해당하는 칼럼 (또는 칼럼의 조합)은 같은
  값을 2개 이상 가질 수 없다. 단, 널 값은 허용된다.

  같은 칼럼 또는 같은 칼럼의 조합에 대해 유니크 제약조건과 기본키를 동시에 정의할
  수 없다. 또한, 같은 칼럼 또는 같은 칼럼의 조합에 대해 2개 이상의 유니크
  제약조건도 존재할 수 없다. 그러나 다른 칼럼 또는 다른 칼럼들의 조합에는 존재할
  수 있다. 최대 32개 칼럼의 조합에 대해 유니크 제약조건을 생성할 수 있다.

- LOCALUNIQUE

  각 지역 인덱스별로 UNIQUE 제약조건을 만족해야 함을 명시하는 키워드이다.

- (NOT) NULL

  해당 칼럼이 널 값을 가질 수 있다(없다)는 것을 의미한다.

- CHECK

  해당 칼럼에 대한 무결성 규칙(Integrity Rule)을 지정한다. *column_constraint*
  절의 *condition* 내에서는 해당 칼럼만 참조할 수 있다. CHECK 제약조건의 검사조건에는 아래와 같은 몇 가지 제한 사항이 있다.

  - 부질의(subquery), 시퀀스, LEVEL 또는 ROWNUM 등의 모든 의사칼럼(Pseudo
    Column), 및 SYSDATE 또는 USER_ID 같은 비결정적(Non-deterministic) SQL 함수가
    포함될 수 없다.
  - PRIOR 연산자를 사용할 수 없다.
  - LOB 타입의 데이터를 사용할 수 없다.

- 참조 무결성(referential integrity)

- TIMESTAMP



*directkey_clause*

이 절은 Direct Key 인덱스를 생성시 사용할 수 있다. Direct Key 인덱스에 대한
자세한 내용은 CREATE INDEX 구문을 참고한다

*check_clause*

이 절에는 테이블의 각 레코드 값이 만족해야 하는 조건을 지정한다. 조건의 결과는
참, 거짓, 또는 NULL 중 하나이어야 한다.

이 절은 칼럼 제약조건 또는 테이블 전체 제약조건이 될 수 있다.

*table_constraint*

한 칼럼 또는 칼럼들의 조합에 대한 제약조건을 명시하는 절이다. 다음의 테이블
제약조건이 있다.

- PRIMARY KEY
- UNIQUE
- LOCALUNIQUE
- CHECK
- 참조 무결성(referential integrity)

*using_index_clause*

제약조건을 위해 자동으로 생성되는 인덱스가 저장될 테이블스페이스를 지정하는
절이다.

PRIMARY KEY, UNIQUE 또는 LOCALUNIQUE 제약을 명시할 경우, 자동으로 생성되는 로컬
인덱스가 저장될 테이블스페이스를 각 인덱스 파티션 별로 지정할 수 있다. 자세한
설명은 CREATE INDEX 구문의 *index_partitioning_clause*를 참조한다.

*references_clause*

외래키를 정의하는 절이다. 외래키에 의해 참조되는 다른 테이블의 참조키(referenced
key)는 그 테이블에서 유니크 제약조건에 해당하거나 그 테이블의 기본키이어야 한다.
만약 이 절에 참조키의 칼럼들을 명시하지 않은 경우, 해당 테이블의 기본키가
자동으로 참조키가 된다.

- NO ACTION

  “부모(parent) 테이블” (참조키가 있는 테이블)에 대해 INSERT, DELETE, 또는 UPDATE
  구문을 실행하면, Altibase는 “자식(child) 테이블” (참조키를 참조하는 외래키를
  가진 테이블)에 대한 무결성 검사를 한 후에 이 구문을 수행한다. NO ACTION은 무결성
  검사 후에 자식 테이블에 대해서는 어떠한 작업도 하지 않음을 명시하는 옵션이다.

  예를 들어 다음과 같이 employees 테이블을 생성하면, departments 테이블에서 어떤
  부서를 삭제하려 할 때, employees 테이블의 레코드가 이 부서 번호를 참조하고
  있다면, 삭제 시도는 실패하고 에러가 발생할 것이다.

  ```
  CREATE TABLE employees (
  ENO INTEGER PRIMARY KEY, 
  DNO INTEGER, 
  NAME CHAR(10), 
  FOREIGN KEY(DNO) REFERENCES 
  departments(DNO) ON DELETE NO ACTION ); 
  
  ```



- ON DELETE CASCADE

  이는 부모 테이블의 행이 삭제되면 외래 키 값을 가진 자식 테이블에서 이 행을
  참조하는 모든 행도 삭제될 것을 명시하는 옵션이다.

  예를 들어 예를 들어 다음과 같이 employees 테이블을 생성하면, departments
  테이블에서 어떤 부서를 삭제하려 할 때, employees 테이블에서 이 부서 번호를
  참조하는 모든 행도 삭제된다.

  ```
  CREATE TABLE employees (
  ENO INTEGER PRIMARY KEY, 
  DNO INTEGER, 
  NAME CHAR(10), 
  FOREIGN KEY(DNO) REFERENCES 
  departments (DNO) ON DELETE CASCADE ); 
  
  ```

- ON DELETE SET NULL

  부모 테이블의 행이 삭제되면 그 행을 참조하는 자식 테이블의 외래 키 칼럼의 값이
  모두 NULL로 변경될 것을 명시하는 옵션이다. 이 옵션의 참조 무결성을 위해 해당
  칼럼은 NULL이 허용되어야 한다.

  예를 들어 departments 테이블을 참조하는 employees 테이블을 생성한 후에,
  departments 테이블에서 어떤 부서를 삭제한다. 이 때, employees 테이블에서 삭제된
  부서 번호를 참조하는 모든 칼럼의 값은 NULL로 변경된다.

  ```
  CREATE TABLE employees (
  ENO INTEGER PRIMARY KEY, 
  DNO SMALLINT, 
  NAME CHAR(10), 
  CONSTRAINT dno_fk FOREIGN KEY (dno) REFERENCES 
  departments (dno) ON DELETE SET NULL ); 
  
  ```



*MAXROWS*

테이블에 입력될 수 있는 최대 레코드 개수를 지정한다. 레코드 삽입시 전체 레코드
개수가 여기에서 지정한 수보다 많아질 경우 입력 시도는 실패하고 에러가 반환된다.
MAXROWS 절은 table_partitioning_clause 절과 함께 명시할 수 없다.

*temporary_attributes_clause*

이 절은 임시 테이블의 데이터가 트랜잭션에 한정되는지 또는 세션에 한정되는지를
지정하며, 아래 두 가지 옵션이 가능하다:

*ON COMMIT DELETE ROWS*

트랜잭션에 한정되는 임시 테이블을 생성한다. 임시 테이블에 처음으로 데이터를
삽입하는 트랜잭션이 그 임시 테이블에 바인딩 된다. 트랜잭션 레벨의 바인딩은
COMMIT 또는 ROLLBACK 구문 수행으로 풀리게 된다. 트랜잭션이 커밋되면, Altibase는
해당 임시 테이블을 truncate 한다.

*ON COMMIT PRESERVE ROWS*

세션에 한정되는 임시 테이블을 생성한다. 세션에서 임시 테이블에 처음으로 데이터가
삽입될 때 세션은 임시 테이블에 바인딩 된다. 이 바인딩은 세션이 종료 되거나 그
세션에서 테이블에 TRUNCATE 작업이 수행 될 때 풀린다. 사용자가 세션을 종료하면,
Altibase는 세션에 바인딩 된 임시 테이블을 truncate 한다.

*table_partitioning_clause*

파티션드 테이블을 생성하는 절이다. 범위 파티셔닝(range partitioning), 해시
파티셔닝(hash partitioning), 리스트 파티셔닝(list partitioning) 방법으로
파티션드 테이블을 생성할 수 있다. 파티션드 테이블을 생성할 때
*row_movement_clause*도 명시할 수 있다.

*range_partitioning*

범위 파티션드 테이블 생성시 파티션 키 값의 범위를 명시하는 절이다. 주로 DATE
자료형에 많이 사용된다. 사용자가 지정한 값을 기준으로 테이블이 분할되기 때문에,
파티션별로 데이터의 고른 분포는 보장되지 않는다. 각 파티션의 범위는 그 범위의
최대값을 설정함으로써 결정된다.

명시된 범위 외의 모든 값과 NULL은 기본 파티션(default partition)에 속하게 된다.
기본 파티션 절은 생략할 수 없다. 여러 칼럼들의 조합으로 파티션 키를 정의할 수
있다.

*table_partition_description*

파티션별로 테이블스페이스를 지정할 수 있다. 또한 테이블에 한 개 이상의 LOB
컬럼이 있을 경우, 각 LOB 컬럼의 속성을 따로 명시할 수 있다. 그리고 파티션의
데이터에 대한 접근 모드를 설정할 수 있다.

테이블스페이스 절이 생략되면, 그 파티션은 해당 테이블의 기본
테이블스페이스(default tablespace)에 저장된다.

또한 LOB 컬럼이 저장될 테이블스페이스를 지정하지 않으면 LOB 데이터는 해당
파티션의 테이블스페이스에 저장된다.

다음의 예제에서 사용자의 기본 테이블스페이스는 tbs_05이다.

```
CREATE TABLE print_media_demo
( 
	product_id INTEGER,
	ad_photo BLOB,
	ad_print BLOB,
	ad_composite BLOB
)
PARTITION BY RANGE (product_id)
(
	PARTITION p1 VALUES LESS THAN (3000) TABLESPACE tbs_01 
	LOB (ad_photo) STORE AS (TABLESPACE tbs_02 ),
	PARTITION p2 VALUES DEFAULT 
	LOB (ad_composite) STORE AS (TABLESPACE tbs_03)
) TABLESPACE tbs_04;

```



파티션 p1의 테이블스페이스는 명시적으로 지정되었으므로 tbs_01테이블스페이스에
저장된다. 그리고 해당 파티션의 ad_photo 컬럼은 tbs_02테이블스페이스에 저장된다.
기본 파티션인 p2의 테이블스페이스는 지정되지 않았으므로 print_media_demo
테이블의 기본 테이블스페이스인 tbs_04에 저장된다. 만약 이 테이블의
테이블스페이스를 지정하지 않았다면 사용자의 기본 테이블스페이스인 tbs_05에
저장될 것이다.

위의 설명을 그림으로 나타내면 다음과 같다.



![create_table_lob](media/SQL/create_table_lob.gif)



*partition_range_clause*

파티션에 저장될 상한값(noninclusive)을 지정한다. 이 값은 다른 파티션의 상한값과
겹치지 않아야 한다.

*hash_partitioning*

이 절은 파티션 키 값에 대응하는 해시 값을 기준으로 테이블을 분할할 것을
명시한다. 이는 데이터가 파티션별로 고르게 분산되기를 원하는 경우에 적합하다.
여러 칼럼들의 조합으로 파티션 키를 정의할 수 있다.

*list_partitioning*

이 절은 값의 집합을 기준으로 테이블을 분할할 것을 명시한다. 명시된 다른 파티션에
속하도록 명시되지 않은 값들은 자동으로 기본 파티션에 포함되기 때문에 기본
파티션은 생략할 수 없다.

기본 파티션에 속해 있던 값들의 집합으로 새로운 파티션을 추가하면 기본
파티션에서는 그 값이 제거될 것이다. 각 파티션이 가질 수 있는 값들은 서로 중복될
수 없기 때문이다. 리스트 파티션드 테이블을 위한 파티션 키는 단일 칼럼에만 정의될
수 있다.

*partition_list_clause*

각 리스트 파티션은 적어도 1개 이상의 값을 가져야 한다. 한 리스트의 값은 다른
어떤 리스트에도 있을 수 없다.

*row_movement_clause*

파티션드 테이블의 레코드가 갱신되어 파티션 키에 해당하는 칼럼의 값이 다른
파티션에 속하는 값으로 변경된 경우, 이 절은 그 레코드를 자동으로 다른 파티션으로
이동시킬지 아니면 에러를 발생시킬 것인지를 결정한다. 이 절을 생략하면 DISABLE
ROW MOVEMENT옵션이 기본으로 설정된다.

*CREATE TABLE … AS SELECT*

테이블 생성시, 다른 테이블에서 새로운 테이블로 칼럼의 속성과 데이터를 그대로
복사하려면 이 구문을 사용한다. 새로운 테이블의 칼럼 수는 SELECT 절로 검색되는
칼럼의 개수와 동일해야 한다. 또한 새로운 칼럼의 데이터 타입은 명시할 수 없고,
데이터가 검색되는 원래 칼럼의 데이터 타입과 동일하게 된다.

생성될 테이블의 칼럼 명을 명시하지 않을 경우에는 검색되는 칼럼의 이름이 그대로
사용된다. 검색 대상이 칼럼이 아니고 표현식인 경우 alias가 반드시 존재해야 한다.
이 alias가 새로운 테이블의 칼럼명이 될 것이다.

*access_mode_clause*

데이터에 대한 접근 모드를 설정할 수 있다. 읽기 전용(Read-Only) 모드,
읽기/쓰기(READ/WRITE) 모드 또는 읽기/추가(READ/APPEND) 모드 중에서 선택할 수
있으며, 생략하면 기본으로 '읽기/쓰기' 모드로 설정된다.

> 주의: 테이블이나 파티션에 대한 접근 모드가 '읽기 전용' 또는 '읽기/추가'로
> 설정되어 있어도 이중화에 의한 복제, TRUNCATE 구문 수행, LOB 칼럼 변경은
> 허용된다.

*tablespace_clause*

테이블이 저장될 테이블스페이스를 지정하는 절이다.

이 절을 생략할 경우 테이블은 이 테이블을 생성하려 하는 사용자의 기본
테이블스페이스에 저장될 것이다. 사용자 생성 시 DEFAULT TABLESPACE를 생략했었다면
테이블은 시스템 메모리 기본 테이블스페이스(SYSTEM MEMORY DEFAULT TABLESPACE)에
생성된다.

CREATE TABLE 문 내에 UNIQUE 또는 PRIMARY KEY 제약조건이 명시된 경우 이들을 위한
인덱스는 테이블이 저장되는 테이블스페이스에 생성될 것이다.

*physical_attributes_clause*

PCTFREE, PCTUSED, INITRANS 및 MAXTRANS를 지정하는 절이다. 이 절이 파티션드
테이블에 명시될 경우 PCTFREE와 PCTUSED 값은 그 테이블의 모든 파티션에 적용될
것이다.

- PCTFREE 절  
  페이지에 이미 저장되어 있는 레코드가 갱신될 때 이용하기 위해 예약해 둔 여유
  공간의 양을 비율로 정의한다. 레코드는 이 예약된 공간 외에만 삽입된다. 이
  값은 한 페이지내의 여유 공간을 백분율로 표시한다.  
  예를 들어 PCTFREE가 20으로 명시된 테이블의 경우, 각 페이지 크기의 80%에만
  레코드가 입력되며, 나머지 20%는 레코드의 갱신 용도로 사용된다. 이 값은
  디스크 기반의 테이블에 대해서만 의미가 있다.  
  명시할 수 있는 값은 0에서 99까지의 정수이며, 백분율을 의미한다. 명시하지
  않을 경우 기본 PCTFREE 값은 10이다. 이 옵션은 테이블에 할당된 페이지에만
  적용된다.
- PCTUSED 절  
  한 페이지가 레코드 삽입이 가능한 상태로 다시 돌아가기 위해 페이지의 사용
  공간이 줄어들어야 하는 최소 비율을 나타낸다. 여유 공간의 비율이 PCTFREE에
  도달한 페이지에는 더 이상 레코드가 삽입되지 않고, 갱신 또는 삭제만 허용된다.
  이후 레코드 갱신 또는 삭제 작업으로 페이지의 사용 공간의 비율이 PCTUSED에서
  명시한 값 이하로 떨어지게 되면 이 페이지는 다시 레코드 삽입이 가능한 상태로
  된다.  
  예를 들어 PCTUSED 값을 40으로 명시한 경우, 어떤 페이지의 여유 공간의 비율이
  PCTFREE에 명시된 값에 도달하면, 이 페이지의 사용 공간 비율이 39% 이하로
  떨어질 때까지 이 페이지에는 레코드 삽입이 불가능하다. 사용 공간의 비율이 40%
  미만으로 떨어져야 비로소 새로운 레코드가 다시 그 페이지에 삽입된다. 이 값은
  디스크 기반 테이블에 대해서만 의미가 있다.  
  명시할 수 있는 값은 0에서 99까지의 정수이며, 백분율을 의미한다. 명시하지
  않을 경우 기본 PCTUSED 값은 40 이다. 이 옵션은 테이블에 할당된 페이지에만
  적용된다.
- INITRANS 절  
  TTS(Touched Transaction Slot)의 초기 개수를 지정한다. 기본값은 2이다.
- MAXTRANS 절  
  TTS(Touched Transaction Slot)의 최대 개수를 지정한다. 기본값은 120이다.

> 참고
>
> 위의 PCTFREE와 PCTUSED는 페이지 사용의 최적화를 위해 다음과 같은 형태로 함께
> 사용된다. 이 예제에서는 PCTFREE는 20, PCTUSED는 40으로 지정하였다.
>
> 각 페이지의 20%는 기존 레코드에 대한 변경 연산을 위한 공간으로 예약되며, 이
> 페이지의 나머지 80%의 공간까지만 새로운 레코드들이 삽입된다.
>
> 이 시점이 되면 더 이상 어떠한 새로운 레코드도 이 페이지에 삽입될 수 없다. 이미
> 저장된 레코드에 대한 갱신과 삭제 연산만이 가능하다. 갱신 연산은 예약해둔 20%의
> 빈 공간을 사용한다. 레코드가 삭제되어 사용중인 공간이 40% 아래로 떨어지면 그
> 페이지에 다시 새로운 레코드를 삽입할 수 있다.
>
> 페이지 공간의 사용은 PCTFREE와 PCTUSED의 값을 이용하여 위와 같은 방법으로 계속
> 순환된다.

*storage_clause*

사용자가 세그먼트에 대한 익스텐트 관리 파라미터를 지정할 수 있는 구문이다.

- INITEXTENTS 절  
  세그먼트 생성시 초기 할당되는 익스텐트 개수를 지정한다. 명시하지 않을 경우
  기본으로 1개의 익스텐트가 할당된다.
- NEXTEXTENTS 절  
  세그먼트 크기 확장시마다 추가될 익스텐트 개수를 명시한다. 명시하지 않을 경우
  기본으로 1개의 익스텐트만큼 확장된다.
- MINEXTENTS 절  
  세그먼트의 최소 익스텐트 개수를 지정한다. 명시하지 않을 경우 기본값은 1이다.
- MAXEXTENTS 절  
  세그먼트가 포함할 수 있는 최대 익스텐트 개수를 지정한다. 명시하지 않을 경우
  제한이 없는 것으로 지정된다.

*LOB_storage_clause*

디스크 테이블의 LOB 칼럼 데이터는 LOB 칼럼이 속한 테이블과 별도의
테이블스페이스에 저장될 수 있다. 그러나 메모리 테이블의 경우는 별도 저장이
불가능하다. 즉, 테이블과 동일한 테이블스페이스에만 저장될 수 있다.

*parallel_clause*

병렬 질의를 처리하는 쓰레드의 개수를 명시한다. 이 절을 생략하면 NOPARALLEL을
지정한 것과 동일하다.

- NOPARALLEL : 쿼리를 병렬로 처리하지 않는다.
- PARALLEL *integer* : integer에 명시한 개수만큼의 쓰레드가 병렬로 쿼리를
  처리한다. 입력 가능한 값의 범위는 1\~65535이다. PARALLEL 1은 NOPARALLEL과
  동일하다.

현재 Altibase는 아래와 같은 병렬 질의만 지원한다.

- 파티션드 테이블을 스캔하는 병렬 질의
- 실행 계획에 HASH, SORT, GRAG 노드가 포함되는 병렬 질의. 단, 이러한 노드의
  경우에는 각 노드당 병렬 작업 쓰레드가 한 개씩만 생성된다.

*table_compression_clause*

압축할 칼럼의 이름을 쉼표로 구분하여 명시한다. MAXROWS 절에는 압축 칼럼당
자동으로 생성되는 딕셔너리 테이블에 입력할 수 있는 행의 최대 개수를 명시한다.
명시하지 않으면 기본값은 일반 테이블과 동일한 2<sup>64</sup>-1개이다.

CREATE TABLE 구문에 이 절과 *subquery*를 모두 명시하여 테이블 생성과 데이터
삽입을 하나의 구문으로 수행하는 것을 지원하지 않는다.

압축이 가능한 데이터 타입과 각 타입 별 최소 크기는 다음과 같다.

| 데이터 타입              | 최소 크기 |
| ------------------------ | --------- |
| CHAR, VARCHAR, BYTE      | 6         |
| NCHAR, NVARCHAR (UTF-8)  | 6         |
| NCHAR, NVARCHAR (UTF-16) | 3         |
| NIBBLE                   | 13        |
| BIT, VARBIT              | 25        |
| DATE                     |           |

#### 주의 사항

다음은 테이블 생성시 유념해야 할 몇 가지 사항이다.

- 정의한 칼럼 크기가 최대 허용 크기를 넘거나 최소 크기 보다 작으면 오류가
  발생한다. 최대와 최소 크기는 각 데이터 타입마다 다르다.
- 한 테이블의 최대 칼럼 수는 1024개이다.
- 기본키는 한 테이블에 한 개만 존재할 수 있다.
- 참조 제약조건의 경우 외래키와 참조키의 칼럼 개수는 동일해야 한다. 또한
  외래키와 참조키의 각 칼럼 데이터 타입은 동일해야 한다.
- 한 테이블에 생성할 수 있는 인덱스, 기본키 및 유니크 키의 총 개수는 1024개를
  넘을 수 없다.
- CREATE TABLE AS SELECT의 경우 칼럼 명을 명시하였다면 그 개수는 검색 대상에
  명시한 칼럼 개수와 동일해야 한다.
- CREATE TABLE AS SELECT문 실행시 CREATE TABLE 문에 칼럼 명을 명시하지 않고
  SELECT문의 검색 대상에는 표현식을 사용한 경우, 반드시 새로운 테이블의 칼럼
  이름으로 사용될 별명(alias name)을 표현식에 명시해야 한다.
- MAXROWS 절에 파티션드 테이블 사용은 지원되지 않는다.
- 범위 파티션드 테이블과 해시 파티션드 테이블을 위한 파티션 키 컬럼은 최대
  32개로 구성될 수 있다.(인덱스 생성 시 인덱스 키 칼럼의 개수 제한과
  동일하다.)
- NOLOGGING(FORCE/NOFORCE) 옵션으로 생성된 인덱스의 경우 시스템이나 미디어
  고장시 인덱스의 일관성이 보장되지 않을 수 있다. 인덱스 일관성이 깨진 경우
  ‘The index is inconsistent.’라는 오류 메시지가 나온다. 이러한 오류를
  해결하려면 일관성이 깨진 인덱스를 찾아 삭제한 후에 해당 인덱스를 다시
  생성하도록 한다. 인덱스의 일관성은 V\$DISK_BTREE_HEADER성능 뷰에서 확인할 수
  있다.
- CREATE INDEX 구문과 마찬가지로 로컬 파티션드 인덱스가 저장될
  테이블스페이스를 지정할 수 없다.
- CREATE TABLE ... AS SELECT의 경우, CHECK 제약조건을 지정할 수 없다.
- PRIMARY KEY, UNIQUE, TIMESTAMP 제약조건을 갖는 칼럼은 압축이 불가능하다.

#### 예제

##### 테이블 생성

다음 테이블들을 생성하라.

- 테이블 이름: employees  
  칼럼: 사원번호, 사원이름과 성, 직책, 전화번호, 부서번호, 월급, 성별, 생일,
  입사일자, 상태

  ```
  iSQL> CREATE TABLE employees(
    eno INTEGER PRIMARY KEY,
    e_lastname CHAR(20) NOT NULL, 
    e_firstname CHAR(20) NOT NULL,
    emp_job VARCHAR(15),
    emp_tel CHAR(15),
    dno SMALLINT,
    salary NUMBER(10,2) DEFAULT 0,
    sex CHAR(1) CHECK(sex IN ('M', 'F')),
    birth CHAR(6),
    join_date DATE,
    status CHAR(1) DEFAULT 'H');
  Create success.
  
  ```



- 테이블 이름: orders  
  칼럼: 주문번호, 주문일자, 판매사원, 고객번호, 상품번호, 주문수량, 도착
  예정일자, 주문상태

  ```
  iSQL> CREATE TABLE orders(
    ono BIGINT,
    order_date DATE,
    eno INTEGER NOT NULL,
    cno BIGINT NOT NULL,
    gno CHAR(10) NOT NULL,
    qty INTEGER DEFAULT 1,
    arrival_date DATE,
    processing CHAR(1) DEFAULT '0', PRIMARY KEY(ono, order_date));
  Create success.
  
  ```



- CREATE TABLE … AS SELECT 사용  
  다음 질의는 직원 테이블에서 부서 번호가 1002인 조건을 만족하는 데이터를 가진
  테이블 dept_1002를 생성한다.

  ```
  iSQL> CREATE TABLE dept_1002
    AS SELECT * FROM employees
    WHERE dno = 1002;
  Create success.
  
  ```



- TIMESTAMP 타입 칼럼을 가지는 테이블을 생성한다.

  ```
  iSQL> CREATE TABLE tbl_timestamp(
  i1 TIMESTAMP CONSTRAINT const2 PRIMARY KEY, 
  i2 INTEGER,
  i3 DATE,
  i4 Byte(8));
  Create success.
  
  ```

   테이블 tbl_timestamp의 속성은 다음과 같다.

  ```
  [ TABLESPACE : SYS_TBS_MEM_DATA ]
  [ ATTRIBUTE ]                                                         
  ------------------------------------------------------------------------------
  NAME                                     TYPE                        IS NULL 
  ------------------------------------------------------------------------------
  I1                                       TIMESTAMP       FIXED       NOT NULL
  I2                                       INTEGER         FIXED       
  I3                                       DATE            FIXED       
  I4                                       BYTE(8)         FIXED       
  [ INDEX ]                                                       
  ------------------------------------------------------------------------------
  NAME                                     TYPE     IS UNIQUE     COLUMN
  ------------------------------------------------------------------------------
  CONST2                                   BTREE    UNIQUE        I1 ASC
  [ PRIMARY KEY ]                                                 
  ------------------------------------------------------------------------------
  I1
  
  ```

  명시적으로 Byte(8) 데이터 타입을 선언한 칼럼 i4와 TIMESTAMP 데이터 타입 칼럼인
  i1을 구별하는 방법은 SYS_CONSTRAINTS_와 SYS_CONSTRAINT_COLUMNS\_ 메타 테이블을
  조회해서 칼럼 타입이 TIMESTAMP 인지를 확인하는 것이다.

  > 참고: INSERT나 UPDATE 수행 시 사용자가 TIMESTAMP 칼럼 값을 DEFAULT로 명시한
  > 경우, 당시의 시스템 시간값이 그 TIMESTAMP 칼럼에 쓰여진다.

  ```
  iSQL> INSERT INTO tbl_timestamp VALUES(DEFAULT, 2, '02-FEB-01', Byte'A1111002');
  1 row inserted.
  iSQL> UPDATE tbl_timestamp SET i1 = DEFAULT, i2 = 102, i3 = '02-FEB-02', i4 = Byte'B1111002' WHERE i2 = 2;
  1 row updated.
  iSQL> SELECT * FROM tbl_timestamp;
  I1                I2          I3           I4
  ------------------------------------------------------------------
  4E3778C900037AE9  102         02-FEB-2002  B111100200000000
  1 row selected.
  
  ```

  마찬가지로 INSERT나 UPDATE 수행 시 사용자가 TIMESTAMP 칼럼 값을 명시하지 않은
  경우, 당시의 시스템 시간 값이 INSERT 또는 UPDATE 수행에 사용된다.

  ```
  iSQL> INSERT INTO tbl_timestamp(i2, i3, i4) VALUES(4, '02-APR-01', Byte'C1111002');
  1 row inserted.
  iSQL> UPDATE tbl_timestamp SET i2=104, i3='02-APR-02', i4=BYTE'D1111002' WHERE i2=4;
  1 row updated.
  iSQL> SELECT * FROM tbl_timestamp;
  I1                I2          I3           I4
  ------------------------------------------------------------------
  4E3778C900037AE9  102         02-FEB-2002  B111100200000000
  4E37794900083702  104         02-APR-2002  D111100200000000
  2 rows selected.
  
  ```



- 임시 테이블 생성 및 사용

  \<질의\> 한 세션에서 임시 테이블을 생성하고 데이터를 삽입한 후, 해당 세션에서는
  데이터가 조회되고, 다른 세션에서는 조회되는 데이터가 없는 것을 보여준다.

  ```
  iSQL> create volatile tablespace my_vol_tbs size 12M autoextend on maxsize 1G; 
  Create success. 
  iSQL> create temporary table t1(i1 integer, i2 varchar(10)) on commit delete rows tablespace my_vol_tbs; 
  Create success. 
  iSQL> create temporary table t2(i1 integer, i2 varchar(10)) on commit preserve rows tablespace my_vol_tbs; 
  Create success. 
  iSQL> desc t2; 
  [ TABLESPACE : MY_VOL_TBS ] 
  [ ATTRIBUTE ]                                                         
  ------------------------------------------------------------------------------ 
  NAME                                     TYPE                        IS NULL 
  ------------------------------------------------------------------------------ 
  I1                                       INTEGER         FIXED       
  I2                                       VARCHAR(10)     FIXED       
  T2 has no index 
  T2 has no primary key 
  iSQL> alter table t2 add constraint t2_pk primary key (i1); 
  Alter success. 
  iSQL> insert into t2 values (1, 'abc'); 
  1 row inserted. 
  iSQL> insert into t2 values (2, 'def'); 
  1 row inserted. 
  iSQL> select * from t2; 
  I1          I2          
  --------------------------- 
  1           abc         
  2           def         
  2 rows selected. 
  iSQL> connect sys/manager; 
  Connect success. 
  iSQL> select * from t2; 
  I1          I2          
  --------------------------- 
  No rows selected.
  
  ```



- 질의에서 지정한 테이블스페이스에 테이블을 생성하라.

  \<질의\> 테이블 소유자가 uare1인 테이블 tbl1을 생성하라. (사용자 생성 시 기본
  테이블스페이스가 지정되지 않았다.)

  ```
  iSQL> CONNECT uare1/rose1;
  Connect success.
  iSQL> CREATE TABLE tbl1(
      i1 INTEGER,
      i2 VARCHAR(3));
  Create success.
  
  ```

  > 참고: 사용자 생성 시 기본 테이블스페이스가 지정되지 않은 경우 시스템 메모리
  > 기본 테이블스페이스에 테이블이 생성 된다.

  \<질의\> 사용자 생성 시 지정된 기본 테이블스페이스 user_data에 다음 조건을
  만족하는 테이블 books과 inventory를 생성하라.

  books 칼럼: 책번호, 책이름, 저자, 판, 출판연도, 가격, 출판사코드 (테이블 books에
  입력할 수 있는 최대 레코드 개수는 2개이다.)

  inventory 칼럼: 예약구독번호, 책번호, 상점코드, 구입날짜, 구입량, 지불여부

  ```
  iSQL> CREATE TABLE books(
    isbn CHAR(10) CONSTRAINT const1 PRIMARY KEY,
    title VARCHAR(50),
    author VARCHAR(30),
    edition INTEGER DEFAULT 1,
    publishingyear INTEGER,
    price NUMBER(10,2),
  pubcode CHAR(4)) MAXROWS 2
  TABLESPACE user_data;
  Create success.
  
  iSQL> CREATE TABLE inventory(
    subscriptionid CHAR(10) PRIMARY KEY,
    isbn CHAR(10) CONSTRAINT fk_isbn REFERENCES books (isbn),
    storecode CHAR(4),
    purchasedate DATE,
    quantity INTEGER,
  paid CHAR(1))
  TABLESPACE user_data;
  Create success.
  
  ```

  또는

  ```
  iSQL> CREATE TABLE inventory(
    subscriptionid CHAR(10),
    isbn CHAR(10),
    storecode CHAR(4),
    purchasedate DATE,
    quantity INTEGER,
    paid CHAR(1),
    PRIMARY KEY(subscriptionid),
  CONSTRAINT fk_isbn FOREIGN KEY(isbn) REFERENCES books(isbn))
  TABLESPACE user_data;
  Create success.
  
  ```

- Direct Key 인덱스를 사용하여 테이블 생성

  \<질의\> 테이블 tab1을 생성할 때 id(INTEGER) 칼럼을 UNIQUE 하면서, Direct Key
  인덱스로 설정한다.

  ```
  iSQL> CREATE TABLE tab1 (id UNIQUE DIRECTKEY );
  Create success.
  
  ```



- 각 인덱스 파티션을 위한 테이블스페이스 지정

  \<질의\> I1 컬럼에 대한 UNIQUE 제약을 갖는 파티션드 테이블 T1을 생성하라.

  ```
  CREATE TABLE T1 
  ( 
    I1 INTEGER UNIQUE USING INDEX LOCAL
    (
      PARTITION P1_UNIQUE ON P1 TABLESPACE TBS3,
      PARTITION P2_UNIQUE ON P2 TABLESPACE TBS2,
      PARTITION P3_UNIQUE ON P3 TABLESPACE TBS1
    )
  )
  PARTITION BY RANGE (I1)
  ( 
    PARTITION P1 VALUES LESS THAN (100),
    PARTITION P2 VALUES LESS THAN (200) TABLESPACE MEM_TBS1,
    PARTITION P3 VALUES DEFAULT TABLESPACE MEM_TBS2 
  ) TABLESPACE SYS_TBS_DISK_DATA;
  
  ```



- 범위 파티셔닝(range partitioning)

  \<질의 1\> 아래 그림과 같이 2006년의 각 분기별로 파티셔닝하여 range_sales
  테이블을 생성한다.

  ```
  CREATE TABLE range_sales
  ( 
    prod_id NUMBER(6),
    cust_id NUMBER,
    time_id DATE
  ) 
  PARTITION BY RANGE (time_id)
  (
    PARTITION Q1_2006 VALUES LESS THAN (TO_DATE('01-APR-2006')),
    PARTITION Q2_2006 VALUES LESS THAN (TO_DATE('01-JUL-2006')),
    PARTITION Q3_2006 VALUES LESS THAN (TO_DATE('01-OCT-2006')),
    PARTITION Q4_2006 VALUES LESS THAN (TO_DATE('01-JAN-2007')),
    PARTITION DEF VALUES DEFAULT 
  ) TABLESPACE SYS_TBS_DISK_DATA;
  
  ```



  \<질의 2\> 파티션의 테이블스페이스를 지정하여 파티션드 테이블 생성

```
  CREATE TABLE T1 
  ( 
    I1 INTEGER, 
    I2 INTEGER 
  )
  PARTITION BY RANGE (I1)
  ( 
    PARTITION P1 VALUES LESS THAN (100),
    PARTITION P2 VALUES LESS THAN (200) TABLESPACE TBS1,
    PARTITION P3 VALUES DEFAULT TABLESPACE TBS2 
  ) TABLESPACE SYS_TBS_DISK_DATA;

```



  \<질의 3\> 다중 컬럼을 파티션 키로 갖는 파티션드 테이블 생성

```
  CREATE TABLE T1 
  ( 
    I1 DATE, 
    I2 INTEGER 
  )
  PARTITION BY RANGE (I1, I2)
  ( 
    PARTITION P1 VALUES LESS THAN (TO_DATE('01-JUL-2006'), 100),
    PARTITION P2 VALUES LESS THAN (TO_DATE('01-JAN-2007'), 200),
    PARTITION P3 VALUES DEFAULT 
  ) TABLESPACE SYS_TBS_DISK_DATA;

```



  \<질의 4\> 필요시 데이터가 자동으로 다른 파티션으로 옮겨지는 파티션드 테이블
  생성

```
  CREATE TABLE T1 
  ( 
    I1 INTEGER, 
    I2 INTEGER 
  )
  PARTITION BY LIST (I1)
  ( 
    PARTITION P1 VALUES (100, 200),
    PARTITION P2 VALUES (150, 250),
    PARTITION P3 VALUES DEFAULT 
  ) ENABLE ROW MOVEMENT TABLESPACE SYS_TBS_DISK_DATA;

```



- 리스트 파티셔닝(list partitioning)

  \<질의\> nls_territory 컬럼의 값이 ‘CHINA’ 또는 ‘THAILAND’인 asia 파티션,
  ‘GERMANY’, ‘ITALY’, ‘SWITZERLAND’인 europe 파티션, ‘AMERICA’인 west 파티션,
  ‘INDIA’인 east 파티션, 그 외 나머지 값은 기본 파티션으로 분할되는 list_customers
  테이블을 생성한다.

  ```
  CREATE TABLE list_customers 
  ( 
  	customer_id	NUMBER(6), 
  	cust_first_name	VARCHAR(20), 
  	cust_last_name	VARCHAR(20), 
  	nls_territory	VARCHAR(30), 
  	cust_email	VARCHAR(30)
  )
  PARTITION BY LIST (nls_territory) 
  (
  	PARTITION asia VALUES ('CHINA', 'THAILAND'),
  	PARTITION europe VALUES ('GERMANY', 'ITALY', 'SWITZERLAND'),
  	PARTITION west VALUES ('AMERICA'),
  	PARTITION east VALUES ('INDIA'),
  	PARTITION rest VALUES DEFAULT 
  ) TABLESPACE SYS_TBS_DISK_DATA;
  
  ```



- 해시 파티셔닝(hash partitioning)

  \<질의\> product_id에 따라서 4개의 해시 파티션으로 분할되는 테이블을 생성한다.

  ```
  CREATE TABLE hash_products 
  ( 
  	product_id		NUMBER(6), 
  	product_name		VARCHAR(50), 
  	product_description 	VARCHAR(2000) 
  )
  PARTITION BY HASH (product_id)
  ( 
  	PARTITION p1, 
  	PARTITION p2, 
  	PARTITION p3, 
  	PARTITION p4 
  ) TABLESPACE SYS_TBS_DISK_DATA;
  
  ```

  \<질의\> LOB 데이터를 별도의 테이블스페이스에 저장하되, image1칼럼은
  테이블스페이스 lob_data1에, image2 칼럼은 테이블스페이스 lob_data2에 저장하는
  테이블을 생성한다.

  ```
  CREATE TABLE lob_products 
  (
    product_id integer, 
    image1 BLOB, 
    image2 BLOB
  ) TABLESPACE SYS_TBS_DISK_DATA
  LOB(image1) STORE AS ( TABLESPACE lob_data1 )
  LOB(image2) STORE AS ( TABLESPACE lob_data2 );
  
  ```

- 세그먼트 내의 익스텐트 관리 파라미터를 지정한 테이블 생성

  \<질의\> 디스크 테이블스페이스인 usertbs에 local_tbl 테이블을 생성한다. 단
  테이블 생성시 익스텐트 10개를 할당하고 세그먼트 확장시마다 1개씩 확장하도록 한다.

  ```
  iSQL> CREATE TABLE local_tbl (i1 INTEGER, i2 VARCHAR(32) ) 
                      TABLESPACE usertbs
                      STORAGE ( INITEXTENTS 10 NEXTEXTENTS 1 );
  Create success.
  
  ```

  \<질의\> 디스크 테이블스페이스인 usertbs에 local_tbl 테이블을 생성한다. 단,
  테이블 생성시 최소 익스텐트 개수는 3으로 하고 최대 익스텐트 개수는 100으로
  제한한다.

  ```
  iSQL> CREATE TABLE local_tbl ( i1 INTEGER, i2 VARCHAR(32) ) 
                      TABLESPACE usertbs
                      STORAGE ( INITEXTENTS 3 MINEXTENTS 3 MAXEXTENTS 100 );
  Create success.
  
  ```



### CREATE DISK TABLESPACE 

#### 구문

**create_disk_tablespace ::=**

![create_disk_tablespace_image137](media/SQL/create_disk_tablespace_image137.gif)

**datafile_spec ::=**

![datafile_spec](media/SQL/datafile_spec.gif)

**autoextend_clause ::=**

![autoextend_clause](media/SQL/autoextend_clause.gif)

**maxsize_clause ::=**

![maxsize_clause](media/SQL/maxsize_clause.gif)

#### 전제 조건

SYS 사용자이거나 CREATE TABLESPACE 시스템 권한을 가진 사용자만이
테이블스페이스를 생성할 수 있다.

#### 설명

데이터베이스 내에 영구적으로 데이터베이스 객체를 저장할 수 있는 디스크
테이블스페이스를 생성하는 구문이다. 이 구문에 의해 생성되는 테이블스페이스에는
테이블과 인덱스가 저장될 수 있다.

*DISK*

디스크 테이블스페이스를 생성한다. DISK 키워드 없이 CREATE TABLESPACE 구문을
실행하여도 디스크 테이블스페이스가 생성된다.

DATA

사용자의 데이터가 저장될 테이블스페이스가 생성된다. DATA 키워드가 없이 CREATE
TABLESPACE 구문을 실행하여도 데이터 테이블스페이스가 생성된다.

*tblspace_name*

생성될 테이블스페이스 이름을 명시한다. 테이블스페이스 이름은  2장 "객체 이름
규칙"을 따라야 한다.

*datafile_spec*

디스크 테이블스페이스를 구성하는 데이터 파일을 명시한다.

*EXTENTSIZE 절*

페이지의 집합인 익스텐트(extent)의 크기를 명시하는 절이다. 생성 시 한번 결정되면
이후 변경할 수 없다. 기본 단위는 kB(킬로바이트, K로 표현됨)이며, MB(메가바이트,
M으로 표현됨), 또는 GB(기가바이트, G로 표현됨) 단위로 크기를 명시할 수 있다.

명시하지 않을 경우 기본값은 한 페이지 크기의 64배이다. 익스텐트 크기를 명시할
경우에는 한 페이지 크기의 배수로 설정해야 한다. 만약 페이지 크기의 배수로
지정하지 않을 경우에는 내부적으로 페이지의 배수에 가장 가까운 값으로 수정되어
처리된다.

또한 디스크 테이블스페이스의 익스텐트 크기는 최소한 페이지 크기의 5배 이상으로
지정해야 한다. 즉 페이지의 크기가 8kB이기 때문에 익스텐트의 크기는 최소한 40kB
이상으로 지정해야 한다.

*SEGMENT MANAGEMENT 절*

디스크 테이블스페이스 생성시 세그먼트 관리 방법을 결정한다. 세그먼트 관리 방법은
테이블스페이스 생성시 옵션으로 선택할 수 있다. 옵션을 명시하지 않으면 새로
생성되는 디스크 테이블스페이스는 프로퍼티 DEFAULT_SEGMENT_MANAGEMENT_TYPE에
설정된 방법으로 관리된다. (기본값은 AUTO이다.)

- MANUAL : 프리 리스트(Freelist) 기반의 테이블스페이스 가용 공간 관리 방식으로
  세그먼트 생성
- AUTO : 비트맵(Bitmap) 인덱스 기반의 테이블스페이스 가용 공간 관리 방식으로
  세그먼트 생성

*file_name*

생성될 데이터 파일 이름을 절대 경로로 명시한다.

*SIZE 절*

데이터 파일의 크기를 명시한다. 이 절을 생략하면, 기본 값은 100MB이다. 기본
크기는 SYS_DATA_FILE_INIT_SIZE 프로퍼티로 변경 가능하다.

정수 값 뒤에 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G)로 단위를 명시할 수
있다. 단위를 명시하지 않을 경우 기본 단위는 Kilobytes(K)이다.

*REUSE*

기존 데이터 파일의 재사용 여부를 지정한다. 명시한 이름을 가진 파일이 이미
존재한다면 반드시 REUSE옵션을 명시해야 한다. 단 존재하는 파일을 재사용할 때에는
기존 데이터가 소실되기 때문에 주의가 필요하다.  
그러나 존재하지 않는 파일 이름에 대해 이 옵션을 사용할 경우 이 옵션은 무시되며,
새로운 파일이 생성된다.

*autoextend_clause*

데이터 파일에 대하여 확장할 수 있는 최대 공간까지 자동으로 확장될지 여부를
명시하는 절이다. 이 절 생략시, 기본으로 자동확장 기능은 꺼진다.

*ON*

파일에 대한 자동 확장 기능이 켜진다.

*OFF*

파일에 대한 자동 확장 기능이 꺼진다.

*NEXT*

파일 크기가 자동으로 확장 될 때 다음에 증가 크기를 명시한다. AUTOEXTEND를 ON으로 하고 이 값을 명시하지 않을 경우, 기본 NEXT 값은
USER_DATA_FILE_NEXT_SIZE 프로퍼티에 지정된 값이다.

Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 로 단위를 명시할 수 있다. 단위를
명시하지 않을 경우 기본 단위는 Kilobytes이다.

*maxsize_clause*

데이터 파일이 자동 확장 가능한 최대 크기를 명시한다. AUTOEXTEND를 ON으로 하고 이
값을 명시하지 않을 경우, 기본값은 USER_DATA_FILE_MAX_SIZE 프로퍼티에 지정된
값이다.

Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 로 단위를 명시할 수 있다. 단위를
명시하지 않을 경우 기본 단위는 Kilobytes이다.

*UNLIMITED*

파일이 자동 확장되는 크기에 제한이 없음을 명시한다. 이 옵션이 사용되면, 실제
파일의 최대 크기는 운영체제 또는 파일 시스템상의 가용 공간의 양에 의해 결정될
것이다.

#### 예제

\<질의\> 다음은 3개의 데이터 파일을 가진 user_data 테이블스페이스를 생성한다.
단, 세그먼트는 “free list” 방식으로 관리되게 한다.

```
iSQL> CREATE TABLESPACE user_data
    DATAFILE '/tmp/tbs1.user' SIZE 10M,
    '/tmp/tbs2.user' SIZE 10M,
    '/tmp/tbs3.user' SIZE 10M
    SEGMENT MANAGEMENT MANUAL;
Create success.
```

\<질의\> 테이블스페이스를 구성하는 데이터 파일이 tbs.user인 10MB의 user_data
테이블스페이스를 생성한다. (user_data 테이블스페이스에 기록되는 테이블이나
인덱스는 tbs.user 파일에 저장될 것이다.)

```
iSQL> CREATE TABLESPACE user_data DATAFILE '/tmp/tbs.user' SIZE 10M AUTOEXTEND
ON;
Create success.
```

\<질의\> User_data 테이블스페이스를 생성한다. 더 큰 공간이 요구될 때 500kB 씩
증가되고 최대 크기 100MB까지 자동 확장된다.

```
iSQL> CREATE TABLESPACE user_data
    DATAFILE '/tmp/tbs.user' SIZE 500K REUSE
    AUTOEXTEND ON NEXT 500K MAXSIZE 100M;
Create success.
```

\<질의\> 자동으로 확장되지 않는 데이터 파일 tbs.user로 구성된 테이블스페이스
user_data를 생성한다.

```
iSQL> CREATE TABLESPACE user_data
    DATAFILE '/tmp/tbs.user' AUTOEXTEND OFF;
Create success.
```



### CREATE MEMORY TABLESPACE 

#### 구문

**create_memory_tablespace ::=**

![create_memory_tablespace_image140](media/SQL/create_memory_tablespace_image140.gif)

**initsize_clause ::=**

![initsize_clause_image141](media/SQL/initsize_clause_image141.gif)

**autoextend_clause ::=**

![autoextend_clause](media/SQL/autoextend_clause.gif)

**maxsize_clause ::=**

![maxsize_clause](media/SQL/maxsize_clause.gif)

**checkpoint_path_clause ::=**

![checkpoint_path_clause_image143](media/SQL/checkpoint_path_clause_image143.gif)

**splitsize_clause ::=**

![splitsize_clause_image144](media/SQL/splitsize_clause_image144.gif)

#### 전제 조건

테이블스페이스는 SYS 사용자이거나 CREATE TABLESPACE 시스템 권한을 가진
사용자만이 테이블스페이스를 생성할수 있다.

#### 설명

데이터베이스 내에 데이터베이스 객체를 저장할 수 있는 메모리 데이터
테이블스페이스를 생성하는 구문이다. 이 구문으로 생성된 테이블스페이스에는 메모리
테이블이 저장될 수 있다.

*MEMORY*

메모리 테이블스페이스를 생성할 것을 지정한다.

*DATA*

사용자의 데이터를 저장할 테이블스페이스를 생성할 것을 지정한다. DATA 키워드 없이
CREATE TABLESPACE 구문을 수행하여도 기본적으로 데이터 테이블스페이스가 생성된다.

*tablespace_name*

생성될 테이블스페이스의 이름을 명시한다. 테이블스페이스 이름은  2장 "객체 이름
규칙"을 따라야 한다.

*initsize_clause*

생성될 테이블스페이스의 초기 크기를 지정한다.

*SIZE*

테이블스페이스의 초기 크기를 명시한다. 이는 메모리 테이블스페이스의 기본 확장 크기의 배수여야 한다. (즉,
EXPAND_CHUNK_PAGE_COUNT 프로퍼티에 지정된 페이지 개수 \* 메모리 테이블스페이스의
한 페이지 크기 (32kB))

예를 들어 EXPAND_CHUNK_PAGE_COUNT프로퍼티를 128로 지정했다면, 메모리
테이블스페이스의 기본 확장 크기는 128 \* 4MB가 될 것이다. 그러므로 초기 크기는
4MB의 배수여야 한다.

이 값은 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 단위로 명시할 수 있다.
단위를 명시하지 않을 경우 기본 단위는 Kilobytes이다.

*autoextend_clause*

테이블스페이스가 자동으로 확장될 지 여부를 명시한다. 이 절을 생략하면,
AUTOEXTEND는 기본으로 꺼진다.

*ON*

AUTOEXTEND 옵션이 켜진다.

*OFF*

AUTOEXTEND 옵션이 꺼진다.

*NEXT*

테이블스페이스가 자동으로 크기가 증가될 때 증가할 양을 명시한다.

단, 이 크기는 메모리 테이블스페이스의 기본 확장 크기의 배수여야 한다.
(EXPAND_CHUNK_PAGE_COUNT 프로퍼티에 지정된 페이지 개수 \* 메모리
테이블스페이스의 한 페이지 크기 (32kB))

AUTOEXTEND를 ON으로 지정하고 이 값을 명시하지 않을 경우, 기본값은
EXPAND_CHUNK_PAGE_COUNT프로퍼티에 지정한 값이다.

AUTOEXTEND가 OFF일 때 이 값은 의미없다. 

이 값은 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 단위로 명시할 수 있다. 단위를 명시하지 않을 경우 기본 단위는 Kilobytes이다.

*maxsize_clause*

테이블스페이스 자동 확장 시 확장할 수 있는 최대 크기를 명시한다. AUTOEXTEND는 ON
으로 지정하고 이 값을 명시하지 않을 경우 기본값은 UNLIMITED이다.

AUTOEXTEND가 OFF이면 이 값은 의미없다.

이 값은 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 단위로 명시할 수 있다. 단위를 명시하지 않을 경우 기본 단위는 Kilobytes이다.

*UNLIMITED*

테이블스페이스가 자동 확장되는 크기에 제한이 없음을 명시한다.

이 옵션이 사용되면, 테이블스페이스는 그 크기가 데이터베이스내의 모든 메모리
테이블스페이스와 모든 휘발성 테이블스페이스의 총 크기가 MEM_MAX_DB_SIZE
프로퍼티에 지정된 크기에 도달할 때까지 자동으로 증가될 것이다.

*checkpoint_path_clause*

메모리 테이블스페이스에 저장된 데이터의 영속성을 보장하기 위해 데이터는 파일에
저장되어야 한다. 이러한 메모리 테이블스페이스의 데이터 저장 파일을 “체크포인트
이미지”라고 한다.

checkpoint_path절은 체크포인트 이미지 파일이 저장될 체크포인트 경로(Path)들을
지정한다. 체크포인트 경로를 지정하지 않은 경우 MEM_DB_DIR 프로퍼티에 지정한 경로가 기본
경로로 사용된다.

*checkpoint_path*

메모리 테이블스페이스의 체크포인트시 체크포인트 이미지가 저장되는 경로이다.
체크포인트 및 테이블스페이스 로딩시 디스크 입출력 비용을 분산할 수 있도록 다수의
경로가 지정될 수 있다.

*split_each_clause*

이 절은 체크포인트 파일을 좀 더 작은 파일로 분리시키기 위해 사용된다. 이는
메모리 테이블스페이스의 크기가 운영체제에서 지원하는 최대 파일 크기를 초과할 때,
또는 입출력 비용을 분산하기 위해서 유용하다. 분할된 파일의 크기는 사용자가
지정할 수 있다. 크기를 지정하지 않을 경우 DEFAULT_MEM_DB_FILE_SIZE 프로퍼티에
지정된 값이 기본으로 사용된다.

이 값은 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 단위로 명시할 수 있다.
단위를 명시하지 않을 경우 기본 단위는 Kilobytes이다.

#### 예제

\<질의 1\> 초기 크기가 512MB이고, 자동 확장되지 않는 사용자 정의 메모리 데이터
테이블스페이스를 생성한다. (체크포인트 이미지는 MEM_DB_DIR 프로퍼티에 지정된
경로에 저장된다. 분할될 체크포인트 이미지 파일의 크기는 DEFAULT_MEM_DB_FILE_SIZE
프로퍼티의 값을 따른다.)

```
iSQL> CREATE MEMORY DATA TABLESPACE user_data SIZE 512M;
Create success.
```

\<질의 2\> 초기 크기가 512MB이고, 128MB 단위로 자동 확장되는[<sup>4</sup>] 사용자 정의
메모리 데이터 테이블스페이스를 생성한다. (체크포인트 이미지는 MEM_DB_DIR
프로퍼티에 지정된 경로에 저장된다. 분할될 체크포인트 이미지 파일의 크기는
DEFAULT_MEM_DB_FILE_SIZE 프로퍼티의 값을 따른다.)

> [<sup>4</sup>] 테이블스페이스의 최대 크기를 MAXSIZE절을 이용하여 지정하지 않았으므로, 기본적으로 UNLIMITTED를 지정한 것과 같다. 이 경우 시스템에 존재하는 모든 메모리
> 테이블스페이스와 휘발성 테이블스페이스의 크기의 총합이 MEM_MAX_DB_SIZE
> 프로퍼티에 지정된 값을 벗어나지 않는 한도 내에서 테이블스페이스의 확장이
> 이루어진다.

```
iSQL> CREATE MEMORY DATA TABLESPACE user_data 
SIZE 512M 
AUTOEXTEND ON NEXT 128M;
Create success.
```

\<질의 3\> 초기 크기가 512MB 이고, 최대 1GB까지 128MB 단위로 자동 확장되는
사용자 정의 메모리 데이터 테이블스페이스를 생성한다. (체크포인트 이미지는
다중화를 위해 3개의 디렉토리에 나누어 저장하고, 분할될 체크포인트 이미지 파일의
크기를 256M로 한다.)

```
iSQL> CREATE MEMORY DATA TABLESPACE user_data 
SIZE 512M AUTOEXTEND ON NEXT 128M MAXSIZE 1G 
CHECKPOINT PATH ‘/dbs/path1’, ‘/dbs/path2’, ‘/dbs/path3’ 
SPLIT EACH 256M;
Create success.
```



### CREATE VOLATILE TABLESPACE 

#### 구문 

**create_tablespace ::=**

![create_tablespace_image145](media/SQL/create_tablespace_image145.gif)

**initsize_clause ::=**

![initsize_clause_image141](media/SQL/initsize_clause_image141.gif)

**autoextend_clause ::=**

![autoextend_clause](media/SQL/autoextend_clause.gif)

**maxsize_clause ::=**

![maxsize_clause](media/SQL/maxsize_clause.gif)

#### 전제 조건

테이블스페이스는 SYS 사용자이거나 CREATE TABLESPACE 시스템 권한을 가진 사용자만
테이블스페이스를 생성할 수 있다.

#### 설명

데이터베이스 내에 데이터베이스 객체를 저장할 수 있는 휘발성 테이블스페이스를
생성하는 구문이다. 이 구문으로 생성한 테이블스페이스에는 휘발성 테이블을 생성할
수 있다.

*VOLATILE*

휘발성 테이블스페이스를 생성할 것을 지정한다.

*DATA*

사용자의 데이터를 저장할 테이블스페이스를 생성할 것을 지정한다. DATA 키워드 없이
CREATE TABLESPACE 구문을 수행하여도 기본으로 데이터 테이블스페이스가 생성된다.

*tablespace_name*

생성될 테이블스페이스의 이름을 명시한다. 테이블스페이스 이름은  2장 "객체 이름 규칙"을 따라야 한다.

*initsize_clause*

생성될 테이블스페이스의 초기 크기를 지정한다.

*SIZE*

테이블스페이스의 초기 크기를 명시한다. 이는 메모리 테이블스페이스의 기본 확장 크기의 배수여야 한다. (즉,
EXPAND_CHUNK_PAGE_COUNT 프로퍼티에 지정된 페이지 개수 \* 메모리 테이블스페이스의
한 페이지 크기 (32kB))

예를 들어 EXPAND_CHUNK_PAGE_COUNT프로퍼티를 128로 지정했다면, 메모리
테이블스페이스의 기본 확장 크기는 128 \* 4MB가 될 것이다. 그러므로 초기 크기는
4MB의 배수여야 한다.

이 값은 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 단위로 명시할 수 있다.
단위를 명시하지 않을 경우 기본 단위는 Kilobytes이다.

*autoextend_clause*

테이블스페이스가 자동으로 확장될 지 여부를 명시한다. 이 절을 생략하면,
AUTOEXTEND는 기본으로 꺼진다.

*ON*

AUTOEXTEND 옵션이 켜진다.

*OFF*

AUTOEXTEND 옵션이 꺼진다.

*NEXT*

테이블스페이스가 자동으로 크기가 증가될 때 증가할 양을 명시한다. 단, 이 크기는 메모리 테이블스페이스의 기본 확장 크기의 배수여야 한다. (EXPAND_CHUNK_PAGE_COUNT 프로퍼티에 지정된 페이지 개수 \* 메모리
테이블스페이스의 한 페이지 크기 (32kB))

AUTOEXTEND를 ON으로 지정하고 이 값을 명시하지 않을 경우, 기본값은
EXPAND_CHUNK_PAGE_COUNT프로퍼티에 지정한 값이다.

AUTOEXTEND가 OFF일 때 이 값은 의미없다.

이 값은 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 단위로 명시할 수 있다.
단위를 명시하지 않을 경우 기본 단위는 Kilobytes이다.

*maxsize_clause*

테이블스페이스 자동 확장 시 확장할 수 있는 최대 크기를 명시한다. AUTOEXTEND는 ON
으로 지정하고 이 값을 명시하지 않을 경우 기본값은 UNLIMITED이다.

AUTOEXTEND가 OFF이면 이 값은 의미없다.

이 값은 Kilobytes(K), Megabytes(M), 또는 Gigabytes(G) 단위로 명시할 수 있다.
단위를 명시하지 않을 경우 기본 단위는 Kilobytes이다.

*UNLIMITED*

테이블스페이스가 자동 확장되는 크기에 제한이 없음을 명시한다.

이 옵션이 사용되면, 테이블스페이스는 그 크기가 데이터베이스내의 모든 메모리
테이블스페이스와 모든 휘발성 테이블스페이스의 총 크기가 MEM_MAX_DB_SIZE
프로퍼티에 지정된 크기에 도달할 때까지 자동으로 증가될 것이다.

#### 예제

\<질의 1\> 초기 크기가 512MB이고, 자동 확장되지 않는 사용자 정의 휘발성 데이터
테이블스페이스를 생성한다.

```
iSQL> CREATE VOLATILE DATA TABLESPACE user_data SIZE 512M;
Create success.
```

\<질의 2\> 초기 크기가 512MB이고, 128MB 단위로 자동 확장되는 사용자 정의 휘발성
데이터 테이블스페이스를 생성한다.

```
iSQL> CREATE VOLATILE DATA TABLESPACE user_data SIZE 512M AUTOEXTEND ON NEXT
128M;
Create success.
```

### CREATE TEMPORARY TABLESPACE 

#### 구문

**create_temporary_tablespace ::=**

![create_temporary_tablespace_image148](media/SQL/create_temporary_tablespace_image148.gif)

**datafile_spec ::=**

![datafile_spec](media/SQL/datafile_spec.gif)

**autoexetend_clause ::=**

![autoextend_clause](media/SQL/autoextend_clause.gif)

#### 전제 조건

SYS 사용자이거나 CREATE TABLESPACE 시스템 권한을 가진 사용자만이 임시
테이블스페이스를 생성할 수 있다.

#### 설명

어떤 세션이 지속되는 동안 사용되는 임시 결과를 저장하기 위한 임시
테이블스페이스를 생성하는 구문이다. 임시 테이블스페이스는 디스크 공간에 생성되고
임시 테이블스페이스의 데이터는 데이터 파일에 저장된다.

데이터베이스 내에 데이터베이스 객체를 영구적으로 저장하려면 CREATE DISK
TABLESPACE 문을 사용하도록 한다.

*tblspace_name*

생성할 임시 테이블스페이스 이름을 명시한다. 테이블스페이스 이름은  2장 "객체 이름 규칙"을 따라야 한다.

*TEMPFILE datafile_space*

임시 테이블스페이스를 구성하는 임시 파일(들)을 명시하는 절이다.

#### 예제

\<질의\> 임시 테이블스페이스를 구성하는 데이터 파일이 tbs.temp인 5MB의 temp_data
테이블스페이스를 생성한다.

```
iSQL> CREATE TEMPORARY TABLESPACE temp_data
  TEMPFILE '/tmp/tbs.temp' SIZE 5M 
  AUTOEXTEND ON; 
Create success.
```



### CREATE TRIGGER

#### 구문

**create_trigger ::=**

![create_trigger](media/SQL/create_trigger.gif)

**simple_dml_trigger ::=**

![simple_dml_trigger_image151](media/SQL/simple_dml_trigger_image151.gif)

**trigger_event ::=**

![trigger_event_image152](media/SQL/trigger_event_image152.gif)

**referencing_clause ::=**

![referencing_clause_image152_1](media/SQL/referencing_clause_image152_1.gif)

**trigger_action::=**

![](media/SQL/9c08ef3d3a9a235c54020897664f1e76.png)

**psm_body::=**

![](media/SQL/9bdcf9256b030ef2f125cae49db1e626.jpg)

**instead_of_dml_trigger::=**

![](media/SQL/15bb3089ca8a5848774adf787ad4e5ed.png)

#### 전제 조건

아래의 조건 중 하나 이상을 만족해야 한다.

- SYS 사용자이다.
- 사용자 자신의 테이블에 트리거를 생성하려면, CREATE TRIGGER 또는 CREATE ANY
  TRIGGER 시스템 권한을 가지고 있어야 한다.
- 다른 사용자의 테이블에 트리거를 생성하려면, CREATE ANY TRIGGER 시스템 권한을
  가지고 있어야 한다.

#### 설명 

명시된 이름으로 트리거를 생성한다.

*OR REPLACE*

이 절은 트리거가 이미 존재한다면 같은 이름의 트리거로 교체할 때 사용된다. 즉, 이
절은 존재하는 트리거를 제거한 후 재생성하는 대신에 기존 트리거의 정의를
변경한다.

*user_name*

생성될 트리거의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 사용자가 소유한
테이블에 트리거를 생성한다.

*trigger_name*

생성될 트리거의 이름을 명시한다. 트리거 이름은 2장 "객체 이름 규칙"을 따라야 한다.

*AFTER*

트리거가 동작될 시점을 지정한다. AFTER 옵션은 *trigger_event*가 수행된 후에
트리거가 동작될 것을 지정한다.

*BEFORE*

BEFORE 옵션은 *trigger_event*가 수행되기 전에 트리거가 동작될 것을 지정한다.

*INSTEAD OF*

INSTEAD OF 옵션은 트리거를 유발한 DML 구문은 수행되지 않고 트리거만 동작할 것을
지정한다. INSTEAD OF 트리거는 뷰에만 생성할 수 있다. 만약 뷰에 LOB 칼럼이 있는
경우 INSTEAD OF 옵션으로 트리거를 생성할 수는 있으나, 트리거의 동작을 유발하는
DML문이 실행될 때 오류가 발생한다.

*trigger_event*

이는 테이블의 데이터를 변경시키는 이벤트로 트리거의 동작을 유발시킨다. 단
데이터베이스의 무결성을 지키기 위해 이중화 수신자에 의해 적용되는 테이블
데이터의 변경은 트리거 이벤트로 처리되지 않는다 (즉, 트리거 동작을 유발시키지
않는다). *trigger_event*로 다음의 세 가지 유형의 DML문을 지정할 수 있다.

- DELETE  
  해당 테이블의 데이터를 삭제하는 DELETE 구문 수행 시 트리거 동작이 유발된다.
- INSERT  
  해당 테이블에 데이터를 삽입하는 INSERT 구문 수행 시 트리거 동작이 유발된다.
  하지만 LOB 칼럼이 있는 테이블에는 'BEFORE INSERT ... FOR EACH ROW' 구문으로
  트리거를 생성할 수는 있으나, 트리거의 동작을 유발하는 DML문이 실행될 때
  오류가 발생한다.
- UPDATE  
  해당 테이블의 데이터를 변경하는 UPDATE 구문 수행 시 트리거 동작이 유발된다.
  UPDATE 트리거 이벤트에 OF 절을 사용할 경우 OF 절에 명시된 컬럼이 변경될
  경우에만 트리거를 동작시킨다.

*ON table_name*

트리거가 동작할지를 결정하기 위해 참조하는 테이블을 지정한다. 트리거는
*table_name*에 정의된 테이블의 변경에 따라 동작이 유발될 것이다.

트리거는 일반 테이블만 참조할 수 있다. 뷰, 시퀀스, 저장 프로시저와 같은 객체를
기반으로 트리거를 생성할 수 없다.

이중화에 포함되어 있는 테이블에는 트리거를 생성할 수 없다. 그러나, 트리거가 이미
존재하는 테이블에 대한 이중화 생성은 가능하다.

User_name이 생략되면, Altibase는 현재 사용자 소유의 테이블을 기반으로 트리거를
생성할 것이다.

*REFERENCING 절*

트리거의 특성상 old row와 new row의 개념을 갖는다. 즉, 트리거가 참조하는
테이블의 데이터 변경시, 변경된 각 row는 이전 값과 이후 값을 갖게 된다.
REFERENCING 절을 사용해서 old row 및 new row를 참조할 수 있다.

REFERENCING 절은 다음과 같은 제약을 갖는다.

- REFERENCING 절은 FOR EACH ROW 옵션과 함께인 경우에만 사용할 수 있다.
- REFERENCING 절은 *trigger_action* 절에서 참조할 수 있도록 다음과 같은 구조를
  가져야 한다.
- {OLD\|OLD ROW\|OLD ROW AS\|OLD AS} alias_name  
  변경되기 이전의 로우(row)를 의미한다. 이는 WHEN 절 또는 trigger_action의
  psm_body 내에서 참조될 수 있다. 트리거 이벤트가 INSERT문일 때는 이전의 값이
  없기 때문에 이전 값 참조는 불가능하다.
- {NEW\|NEW ROW\|NEW ROW AS\|NEW AS} alias_name  
  변경된 후의 로우(row)를 의미한다. 단, BEFORE TRIGGER의 경우 트리거 바디
  내에서 이들 데이터를 변경하는 것이 가능하다. 트리거 이벤트가 DELETE문일 경우
  이후 값이 없기 때문에 이후 값 참조는 불가능하다.

*trigger_action*

트리거 작동 절은 다음과 같은 세 가지 부분으로 구성된다.

- Action granularity: 트리거가 수행되는 단위 지정 (ROW 또는 STATEMENT)
- Action WHEN condition: 트리거 동작 여부를 결정하는 추가 조건을 선택적으로
  명시
- Action body: 트리거가 실제로 무엇을 수행하는지 명시

*FOR EACH {ROW\|STATEMENT}*

트리거 수행 단위를 명시한다. 테이블의 데이터 변경시 여기에 명시된 단위에 따라서
트리거가 발생한다. 기본값은 FOR EACH STATEMENT이다.

- FOR EACH ROW: trigger_event에 의해 영향을 받고 WHEN 절의 조건을 만족하는 각
  row에 대해서 트리거의 action body 가 수행된다.  
  REFERENCING 절 또는 WHEN 절을 사용하기 위해서는 반드시 FOR EACH ROW 절을
  사용하여야 한다.
- FOR EACH STATEMENT: 트리거 동작을 유발하는 DML 구문의 수행 후 또는 전에 한
  번만 트리거가 동작하게 된다.

*WHEN search_condition*

트리거가 동작 여부를 결정하는 조건을 명시한다. WHEN 절의 *search_conditio*n이
TRUE 인 경우에만 트리거의 action body가 수행되며, FALSE인 경우에는 트리거의
action body가 수행되지 않는다. WHEN 절이 명시되지 않으면, 트리거 이벤트 발생 시
항상 트리거의 action body가 수행된다.

WHEN 절에 조건을 사용하기 위해서는 다음과 같은 제약을 만족해야 한다.

- WHEN 절은 반드시 FOR EACH ROW 절과 함께인 경우에만 사용할 수 있다.
- WHEN 절에는 REFERENCING절에 정의된 alias_name만을 사용할 수 있다.
- WHEN 절에는 부질의를 사용할 수 없다.
- WHEN 절에는 저장 프로시저를 사용할 수 없다.

*psm_body*

트리거의 “action body”를 의미하며, 트리거가 수행할 구문이 여기에 기술된다. 저장
프로시저의 블록 구문과 동일한 방법으로 기술할 수 있다.

Psm_body는 다음과 같은 제약을 만족하여야 한다.

트리거의 특성 및 개념 상 action body를 위한 SQL statement 구문은 다음과 같은
것을 사용할 수 없다.

- COMMIT 또는 ROLLBACK 등과 같은 트랜잭션 관련구문을 사용할 수 없다.
- CONNECT 등과 같은 세션 관련구문을 사용할 수 없다.
- CREATE TABLE 등과 같은 스키마 관련구문을 사용할 수 없다.
- 저장 프로시저를 호출할 수 없다.
- 회기하는 트리거, 즉 trigger_event에 명시된 연산을 수행하는 트리거는 생성할
  수 없다.

*ENABLE \| DISABLE*

사용자가 트리거를 생성할 때 활성화(enable) 또는 비활성화(disable)를 선택할 수
있다. 기본 값은 활성화 상태이다.

- 트리거를 생성할 때 비활성화 상태로 설정하면 동작하지 않으며, ALTER TRIGGER
  구문으로 트리거 상태를 변경할 수 있다.

저장 프로시저의 블록 구문에 대한 자세한 설명은 *Stored Procedures Manual*을
참조하기 바란다.

#### 주의 사항

- 트리거의 수행 순서  
  하나의 테이블에 대하여 하나 이상의 트리거를 정의할 수 있다. 여러 개의
  트리거가 정의되어 있을 때 트리거가 동작되는 순서는 일정하지 않다. 트리거
  동작 순서가 중요할 경우에는 여러 개의 트리거를 하나로 통합하여 재작성 하여야
  한다.
- 트리거의 수행 실패  
  트리거를 수행하던 도중 오류가 발생하면, 해당 트리거를 발생시킨 DML 구문도
  실패하게 된다.
- 트리거 내에서 참조되는 테이블에 발생하는 DDL  
  테이블이 삭제되면 그 테이블에 대해 생성되어 있는 모든 트리거도 삭제된다.  
  그러나 트리거의 action body내에서 참조하는 테이블이 변경되거나 삭제될
  경우에는 트리거는 제거되지 않는다. 참조 테이블이 삭제되어 해당 트리거의
  action body가 수행될 수 없는 경우, 그 트리거를 발생시킨 DML 구문은 실패할
  것이다. 참조 테이블이 변경된 경우에는 트리거 발생시에 트리거가 내부적으로 재
  컴파일되어 정상적으로 수행될 것이다.
- 트리거와 이중화  
  이중화로 인해 반영되는 테이블 데이터의 변경은 트리거 동작을 발생시키지
  않는다.

#### 예제

\<질의\> 다음 예제는 행의 삭제를 추적하기 위해 트리거를 어떻게 사용하는지를
보여준다. 이 예제에서 배달이 완료(processing=’D’)된 주문에 관련된 데이터가
orders 테이블에서 삭제될 때, 트리거는 FOR EACH ROW 기준으로 동작되고 orders
테이블의 ono, cno, qty 및 arrival_date 칼럼의 원래 값을 참조한다. 이 트리거는
orders 테이블에서 삭제된 행의 값을 log_tbl에 입력한다.

```
iSQL> CREATE TABLE log_tbl(
  ono BIGINT,
  cno BIGINT,
  qty INTEGER,
  arrival_date DATE,
  sysdate DATE);
Create success.

iSQL> CREATE TRIGGER del_trigger
  AFTER DELETE ON orders
  REFERENCING OLD ROW old_row
  FOR EACH ROW
  AS BEGIN
    INSERT INTO log_tbl VALUES(old_row.ono, old_row.cno, old_row.qty, old_row.arrival_date, sysdate);
  END;
/
Create success.

iSQL> DELETE FROM orders WHERE processing = 'D';
2 rows deleted.
iSQL> SELECT * FROM log_tbl;
ONO                  CNO                  QTY         ARRIVAL_DATE
------------------------------------------------------------------------
SYSDATE
---------------
11290011             17                   1000        05-DEC-2011
25-APR-2012
11290100             11                   500         07-DEC-2011
25-APR-2012
2 rows selected.
```

\<질의\> 다음의 예제에서, 트리거는 scores 테이블에 레코드가 입력될 때, score
칼럼의 값이 지정되어 있지 않으면(NULL이면) 이 값을 0으로 변경한다. 이를 위해서
FOR EACH ROW 기준으로 발생되는 BEFORE INSERT 트리거를 생성하면 된다.

```
iSQL> CREATE TABLE scores( id INTEGER, score INTEGER );
Create success.
iSQL> CREATE TRIGGER scores_trigger
BEFORE INSERT ON scores
REFERENCING NEW ROW NEW_ROW
FOR EACH ROW
AS BEGIN
  IF NEW_ROW.SCORE IS NULL THEN
     NEW_ROW.SCORE := 0;
  END IF;
END;
/
Create success.

iSQL> INSERT INTO scores VALUES( 1, 20 );
1 row inserted.
iSQL> INSERT INTO scores VALUES( 5, NULL );
1 row inserted.
iSQL> INSERT INTO scores VALUES( 17, 75 );
1 row inserted.

iSQL> SELECT * FROM SCORES;
ID          SCORE       
---------------------------
1           20          
5           0           
17          75          
3 rows selected.
```

\<질의\> 트리거를 비활성화(disable) 상태로 생성하여 동작을 확인한 후에
활성화(enable) 상태로 변경하여 동작을 확인한다.

```
iSQL> CREATE TABLE scores( id INTEGER, score INTEGER );
Create success.

iSQL> CREATE TRIGGER scores_trigger
BEFORE INSERT ON scores
REFERENCING NEW ROW NEW_ROW
FOR EACH ROW
DISABLE
AS BEGIN
IF NEW_ROW.SCORE IS NULL THEN
NEW_ROW.SCORE := 0;
END IF;
END;
/
Create success.

iSQL> INSERT INTO scores VALUES( 1, 20 );
1 row inserted.
iSQL> INSERT INTO scores VALUES( 5, NULL );
1 row inserted.
iSQL> INSERT INTO scores VALUES( 17, 75 );
1 row inserted.

iSQL> SELECT * FROM SCORES;
ID SCORE
---------------------------
1 20
5
17 75
3 rows selected.

iSQL> ALTER TRIGGER scores_trigger ENABLE;
Alter success.

iSQL> INSERT INTO scores VALUES( 100, NULL );
1 row inserted.

iSQL> SELECT * FROM SCORES;
ID SCORE
---------------------------
1 20
5
17 75
100 0
4 rows selected.
```



### CREATE USER 

#### 구문

**create_user ::=**

![create_user_image155](media/SQL/create_user_image155.gif)

**<a name="password_parameters"><a/>**

**password_parameters ::=**

![password_parameters](media/SQL/password_parameters.gif)

#### 전제 조건

SYS 사용자와 CREATE USER 시스템 권한을 가진 사용자만이 사용자를 생성할 수 있다.

#### 설명

명시된 사용자 이름, 암호, 테이블스페이스 접근 권한으로 데이터베이스 사용자를
생성하는 구문이다.

*user_name*

생성될 사용자 이름을 명시한다. 사용자의 이름은 데이터베이스 내에서 유일해야
한다. 사용자 이름은 2장의 "객체 이름 규칙"을 따라야 한다.

*IDENTIFIED BY password*

Altibase는 비밀 번호를 사용해서 사용자를 인증한다. 사용자 비밀 번호의 최대
길이는 40바이트이다. 만일 이보다 더 긴 문자열의 비밀 번호를 명시하여 사용자를
생성하면, 오류가 반환된다. 비밀 번호는 기본적으로 대소문자 구분 없이 대문자로
인식된다. 만약 사용자 암호의 대소문자를 구분하기 위해서는
CASE_SENSITIVE_PASSWORD 프로퍼티를 1로 설정한 다음, CREATE USER 구문으로
사용자를 생성할 때 암호를 큰따옴표(")로 묶는다.

사용자 비밀 번호는 2장의 "객체 이름 규칙"을 따라야 한다.

*TEMPORARY TABLESPACE 절*

이는 사용자가 테이블에 연산 수행시 중간 결과가 저장될 용도로 사용될 기본 임시
테이블스페이스(DEFAULT TEMPORARY TABLESPACE)를 지정하는 절이다.

이를 명시하지 않으면 시스템 임시 테이블스페이스<sup>[5]</sup>가 해당 사용자의 기본 임시
테이블스페이스로 지정된다.

> <sup>[5]</sup>: SYSTEM TEMPORARY TABLESPACE는 쿼리 수행 중에 발생되는 임시 데이타들을 저장하는데 사용된다. 로깅이 수행되지 않기 때문에 매체 오류시 이 테이블스페이스의
> 데이터는 복구가 불가능하다.

사용자가 디스크 기반 테이블에 대한 SQL문을 수행할 때 일반적으로 임시
테이블스페이스가 사용된다. 

만약 SQL문내의 모든 테이블들이 메모리에 존재하는 테이블이라면, 쿼리 수행시
Altibase가 사용하는 공간도 모두 메모리이며, 사용자가 힌트를 사용하지 않는다면
임시 테이블스페이스를 사용하지 않는다.

임시 테이블스페이스는 한 사용자에 하나만 지정할 수 있다.

*DEFAULT TABLESPACE 절*

사용자가 생성한 객체를 저장할 기본 테이블스페이스를 명시한다. 이 절을 생략하면
시스템 메모리 기본 테이블스페이스가 사용자의 기본 테이블스페이스가 된다.

기본 테이블스페이스는 한 사용자에 하나만 지정할 수 있다.

*ACCESS 절*

명시한 (*tablespace_name*) 테이블스페이스에 접근 가능 여부를 지정하는 절이다.
ACCESS *tablespace_name* ON으로 지정한 테이블스페이스에 대해서는 사용자는 접근
권한을 부여 받는다. OFF로 명시한 테이블스페이스에 대해서는 사용자가 접근이
불가능하다.

물론, ALTER TABLESPACE 시스템 권한이 부여된 사용자는 테이블스페이스 접근이
가능하다.

*ENABLE/ DISABLE*

사용자의 TCP 접속을 허용하거나 제한할 수 있다. 이 절은 SYS 사용자만 수행할 수
있다.

*FAILED_LOGIN_ATTEMPTS*

로그인을 시도할 때 이 값에 설정한 횟수만큼 실패하면 해당 계정은 잠금이 해제될
때까지 로그인이 불가능하다.  
PASSWORD_LOCK_TIME이 설정되어 있는 경우 해당 기간이 경과하면 잠금이 자동으로
해제된다.

*PASSWORD_LOCK_TIME*

차단된 계정이 해제되기 위해 경과되어야 하는 날짜(단위: 일)를 지정한다. 예를
들어, 이 값을 5로 지정했을 때 계정이 잠긴다면, 해당 계정은 5일이 지난 후에
잠금이 풀리고 로그인이 가능해진다.

*PASSWORD_LIFE_TIME*

계정의 패스워드가 유효한 기간(단위: 일)을 지정한다. 마지막으로 패스워드를 변경한
시점을 기준으로 PASSWORD_LIFE_TIME이 적용된다.

*PASSWORD_GRACE_TIME*

계정의 패스워드가 만료된 이후의 변경할 수 있는 유예 기간(단위: 일)을 지정한다.
패스워드 유효 기간이 만료되면 유예 기간이 경과하기 전에 해당 계정으로 로그인하여
패스워드를 변경해야 한다. 만약 패스워드 유예기간도 경과하면, SYS 계정으로
로그인하여 해당 계정의 패스워드를 변경해야 한다.

*PASSWORD_REUSE_TIME*

동일한 패스워드를 재사용하기 위해 경과해야 하는 기간(단위:일)을 지정한다. 즉,
여기에 설정한 기간이 지난 후에 동일한 패스워드를 재사용할 수 있다.

*PASSWORD_REUSE_MAX*

동일한 패스워드를 재사용하기 위한 패스워드 변경 횟수를 지정한다. 즉, 여기에
설정한 횟수만큼 패스워드를 변경한 후에 동일한 패스워드를 재사용할 수 있다.

> 주의: PASSWORD_REUSE_MAX 또는 PASSWORD_REUSE_TIME 중 하나만 지정하면, 동일한
> 패스워드를 재사용할 수 없다.

*PASSWORD_VERIFY_FUNCTION*

여기에 사용자 정의 콜백 함수(CALLBACK function)를 등록하여 패스워드를 검증하도록
할 수 있다. 사용자 정의 콜백 함수는 반드시 'TRUE'를 반환해야 한다.

패스워드 검증용 콜백 함수는 아래와 같은 입력 파라미터와 반환 타입을 가져야 한다:

```
CREATE OR REPLACE FUNCTION pwd_verify_function (
  username varchar(20),
  password varchar(20))
  RETURN varchar(100)
AS
result        varchar(100);
...
BEGIN
    ...
    result := 'TRUE';
    RETURN result;
END;
/
```



#### 제한 사항

한 사용자는 여러 데이터 테이블스페이스를 사용할 수 있다. 그러나 한 사용자는 임시
테이블스페이스는 하나만 사용할 수 있다.

사용자가 명시적으로 시스템 언두 테이블스페이스에 접근하거나, 언두 테이블스페이스
내에 테이블이나 인덱스 등을 생성하는 것은 불가능하다. 또한, 시스템 언두
테이블스페이스는 데이터베이스 내에 오직 하나만 존재하며, 사용자가 이를
생성하거나 삭제할 수 없다.

#### 예제

\<질의\> 사용자 명이 uare1이고 암호가 rose1인 사용자를 생성하라.

```
iSQL> CREATE USER uare1 IDENTIFIED BY rose1;
Create success.
```

\<질의\> 사용자 이름이 uare4이고 암호가 rose4인 사용자를 생성하라. 또한
user_data를 사용자의 기본 테이블스페이스로, temp_data 테이블스페이스를 임시
테이블스페이스로 사용하며, 메모리 테이블스페이스인 SYS_TBS_MEMORY에 대해 접근
권한을 가지고 있다.

```
iSQL> CREATE USER uare4
        IDENTIFIED BY rose4
        DEFAULT TABLESPACE user_data
        TEMPORARY TABLESPACE temp_data
        ACCESS SYS_TBS_MEMORY ON;
Create success.
```

\<질의\> 로그인을 5번 실패하면 해당 계정이 잠기고, 5일 후에 잠금이 풀리게 되는
사용자 rose2를 생성한다.

```
iSQL> CREATE USER rose2 IDENTIFIED BY rose2 
  LIMIT (FAILED_LOGIN_ATTEMPTS 5, PASSWORD_LOCK_TIME 5);
```

\<질의\> 5일 후에 패스워드가 만료되고, 그 후 5일간 유예기간을 갖는 사용자
rose3을 생성한다.

```
iSQL> CREATE USER rose3 IDENTIFIED BY rose3
  LIMIT (PASSWORD_LIFE_TIME 5, PASSWORD_GRACE_TIME 5);
```

\<질의\> 패스워드를 3회 변경하고 10일이 지난 후에 동일한 패스워드를 재사용할 수
있는 사용자 rose4를 생성한다.

```
iSQL> CREATE USER rose4 IDENTIFIED BY rose4
  LIMIT (PASSWORD_REUSE_MAX 3, PASSWORD_REUSE_TIME 10);
```



### CREATE VIEW

#### 구문

**create_view ::=**

![create_view_image156](media/SQL/create_view_image156.gif)

**query_restriction_clause ::=**

![query_restriction_clause_image157](media/SQL/query_restriction_clause_image157.gif)

#### 전제 조건

아래의 조건 중 하나 이상을 만족해야 사용할 수 있다.

- SYS 사용자이다.
- 사용자 자신의 스키마에 테이블을 생성하려면, CREATE TABLE 또는 CREATE ANY
  TABLE 시스템 권한을 가지고 있어야 한다.
- 다른 사용자의 스키마에 테이블을 생성하려면, CREATE ANY TABLE 시스템 권한을
  가지고 있어야 한다.

#### 설명

명시된 이름으로 새로운 뷰를 생성한다. 뷰(view)란 하나 이상의 테이블 또는 뷰를
기반으로 하는 논리적인 테이블(logical table)이다. 뷰는 실제 데이터를 가지고 있지
않다. 뷰의 기반이 된 테이블을 베이스 테이블(base table)이라 한다.

*OR REPLACE*

이 절은 뷰가 이미 존재한다면 같은 이름의 뷰로 교체할 때 사용된다. 즉, 이 절은
존재하는 뷰를 제거한 후 재 생성하는 대신에 기존 뷰의 정의를 변경하는 기능을
제공한다.

*FORCE*

뷰의 베이스 테이블 존재 여부와 뷰를 내포하고 있는 스키마 소유자의 권한 유무에
상관없이 뷰가 생성되도록 하는 옵션이다.

이는 의미상으로 오류를 내포한 무효한 상태의 뷰가 생성될 수 있음을 의미한다. 이런
경우, 뷰에 대해 SELECT 문 수행 시 오류가 발생할 것이기 때문에, FORCE 옵션을
사용해 뷰를 생성한 후에는 뷰를 SELECT 해보거나 SYS_VIEWS\_ 메타 테이블을 조회해
뷰의 상태를 확인해야 한다.

*NO FORCE*

이 옵션을 사용하면 뷰의 베이스 테이블이 존재하고 뷰를 내포하고 있는 스키마
소유자가 권한을 가지고 있을 때만 뷰가 생성된다. 이 옵션이 기본값이다.

*user_name*

생성될 뷰의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 세션에 연결된
사용자의 스키마에 뷰를 생성한다.

*view_name*

생성될 뷰의 이름을 명시한다. 뷰의 이름은 2장 "객체 이름 규칙"을 따라야 한다.

*alias_name*

베이스 테이블로부터 검색하는 대상이 표현식인 경우 표현식을 위한 별칭을 명시해야
한다. 이 별칭이 뷰의 칼럼 명이 된다. 별칭의 개수는 subquery의 검색 대상(표현식과
칼럼)의 총 개수와 동일해야 한다.

*subquery*

베이스 테이블로부터 조회하는 열과 행을 식별하는 부질의를 명시한다.

*WITH READ ONLY*

뷰가 읽기 전용임을 지정할 수 있다. 이 옵션을 명시하지 않으면, INSERT, UPDATE,
DELETE 같은 변경 연산을 수행할 수 있는 Updatable View가 생성된다.

#### 주의 사항

- 뷰가 저장된 스키마의 소유자는 뷰의 기반이 되는 테이블 또는 뷰로부터 SELECT
  문을 수행하는데 필요한 권한을 가지고 있어야 한다.
- 베이스 테이블에 대한 SELECT문의 검색 대상에 명시할 수 있는 표현식의 개수는
  최대 1024개이다.
- CURRVAL과 NEXTVAL 의사열을 베이스 테이블에 대한 SELECT문의 검색 대상에
  사용할 수 없다.

#### 예제

##### 뷰 생성하기

\<질의\> 다음 예제는 employees 테이블을 기반으로 한 이름이 avg_sal인 뷰를
생성한다. 뷰는 각 부서의 평균 월급을 부서별로 보여준다.

```
iSQL> CREATE VIEW avg_sal AS
  SELECT dno, AVG(salary) emp_avg_sal
FROM employees
  GROUP BY dno;
Create success.
iSQL> SELECT * FROM avg_sal;
AVG_SAL.DNO  AVG_SAL.EMP_AVG_SAL 
------------------------------------
A001  2066.66667  
C001  1576.66667  
C002  1660     
D001  2075.75   
F001  1845     
                  
6 rows selected.
```

부질의 내에서 표현식 AVG(salary)에 대한 별칭으로 emp_avg_sal이 제공되어 있기
때문에, 뷰의 칼럼을 위한 별칭은 명시할 필요가 없다.

##### 조인 뷰<sup>[6]</sup> 생성하기

> <sup>[6]</sup>:조인 뷰는 뷰의 부질의에 조인을 내포하는 것을 의미한다.

\<질의\> 다음 뷰는 주문된 상품을 담당하고 있는 사원 이름과 상품을 주문한 고객의
이름을 보여준다.

```
iSQL> CREATE VIEW emp_cus AS 
 SELECT DISTINCT e.e_firstname, e.e_lastname, 
  c.c_firstname, c.c_lastname 
 FROM employees e, customers c, orders o 
 WHERE e.eno = o.eno AND o.cno = c.cno;
Create success.
iSQL> SELECT * FROM emp_cus;
E_FIRSTNAME           E_LASTNAME            C_FIRSTNAME           C_LASTNAME
---------------------------------------------------------------------------------------------
Alvar                 Marquez               Estevan               Sanchez
Sandra                Hammond               Pierre                Martin
.
.
.
William               Blake                 Saeed                 Pahlavi
Sandra                Hammond               Saeed                 Pahlavi
22 rows selected.
```



### CREATE MATERIALIZED VIEW

#### 구문

**create_materialized_view ::=**

![create_mview](media/SQL/create_mview.gif)

[table_partitioning_clause ::=](#table_partitioning_clause), [tablespace_clause
::=](#tablespace_clause), [logging_clause ::=](#logging_clause),
[lob_column_properties ::=](#lob_column_properties)

**physical_attributes_clause ::=**

![physical_attributes_clause](media/SQL/physical_attributes_clause.gif)

[storage_clause ::=](#storage_clause)

**build_clause ::=**

![build_clause](media/SQL/build_clause.gif)

**refresh_clause ::=**

![refresh_clause](media/SQL/refresh_clause.gif)

#### 전제 조건

아래의 조건 중 하나 이상을 만족해야 사용할 수 있다.

- SYS 사용자이다.
- 사용자 자신의 스키마에 materialized view를 생성하려면, CREATE MATERIALIZED
  VIEW 또는 CREATE ANY MATERIALIZED VIEW 시스템 권한을 가지고 있어야 한다.
  또한, 자신의 소유가 아닌 베이스 테이블 각각에 대한 SELECT 객체 권한 또는
  SELECT ANY TABLE 시스템 권한이 있어야 한다.
- 다른 사용자의 스키마에 materialized view를 생성하려면, CREATE ANY
  MATERIALIZED VIEW 시스템 권한을 가지고 있어야 한다. 또한, 소유자의 소유가
  아닌 베이스 테이블 각각에 대한 SELECT 객체 권한 또는 SELECT ANY TABLE 시스템
  권한이 있어야 한다.
- Materialized view를 생성하면, materialized view 객체와 함께 데이터베이스
  내부적으로 사용될 한 개의 뷰와 한 개의 테이블이 자동으로 materialized view의
  스키마에 생성된다. 추가로 생성되는 이러한 객체들은 materialized view의
  데이터를 유지하기 위해 사용된다. Materialized View를 생성하려는 사용자는
  이러한 객체들을 생성하는데 필요한 권한을 가지고 있어야 한다.

#### 설명

명시된 이름으로 새로운 materialized view를 생성한다. Materialized view란 쿼리의
결과를 저장하고 있는 데이터베이스 객체이다. 쿼리의 FROM 절에는 테이블, 뷰, 및
다른 materialized view가 올 수 있다. 이러한 객체들을 "베이스 테이블"이라고 한다.

Materialized view는 쿼리문의 결과를 일반 테이블처럼 테이블스페이스에 저장하며,
주로 데이터 웨어하우스 목적으로 사용된다. 즉, 빈번히 실행되며 수행에 많은 시간이
소요되는 조인이나 집계 함수가 포함된 쿼리문을 materialized view로 생성해 두면,
쿼리 실행 시 수행 시간을 단축할 수 있다.

Altibase는 읽기 전용 materialized view만 제공한다.

*user_name*

생성될 materialized view의 소유자 이름을 명시한다. 생략하면 Altibase는 현재
세션에 연결된 사용자의 스키마에 materialized view를 생성한다.

*mview_name*

생성될 materialized view의 이름을 명시한다. materialized view의 이름은 2장 "객체 이름 규칙"을 따라야 한다. Altibase는 지정한 materialized view의 이름과 동일한 이름으로 materialized view의 데이터를 유지하기
위해 사용되는 테이블을 자동으로 생성한다.

*c_alias*

베이스 테이블로부터 검색하는 대상이 표현식인 경우 표현식을 위한 별칭을 명시해야
한다. 이 별칭이 materialized view의 칼럼 명이 된다. 별칭의 개수는 subquery의
검색 대상(표현식과 칼럼)의 총 개수와 동일해야 한다.

*table_partitioning_clause*

CREATE TABLE 구문의 *table_partitioning_clause* 설명을 참고하라.

*segment_attributes_clause*

CREATE TABLE 구문의 *segment_attributes_clause* 설명을 참고하라.

*lob_column_properties*

CREATE TABLE 구문의 *lob_column_properties* 설명을 참고하라.

*phsical_attributes_clause*

CREATE TABLE 구문의 *phsical_attributes_clause* 설명을 참고하라.

*build_clause 절*

이 절은 Materialized view의 데이터가 최초로 구축되는 시점을 지정한다. 이 절을
생략하면 기본값은 IMMEDIATE이다.

- IMMEDIATE: Materialized view가 생성되는 시점에 데이터 구축.
- DEFERRED: Materialized view이 생성된 후 리프레쉬가 수행될 때 데이터 구축.

*refresh_clause 절*

Materialized view의 베이스 테이블이 변경되면, materialized view의 데이터도
업데이트되어야 한다. 이 절은 Materialized view가 refresh되는 방법과 시기를
지정한다. 이 절을 생략하면 FORCE와 ON DEMAND가 기본값으로 설정된다.

REFRESH 키워드 뒤에 COMPLETE, FAST, FORCE 중의 하나 또는 ON DEMAND, ON COMMIT
중의 하나는 반드시 지정되어야 한다.

- COMPLETE: Materialized view를 생성할 때 정의한 subquery를 수행하여 데이터가
  구축될 것을 지정한다.
- FAST: 현재 미지원.
- FORCE: refresh가 발생할 때, fast refresh가 가능하면 수행하고, 그렇지 않으면
  complete refresh로 수행할 것을 데이터베이스에 지시한다. Altibase는 현재
  FAST를 지원하지 않으므로, FORCE를 지정하는 것은 COMPLETE를 지정한 것과
  동일하다.
- ON DEMAND: 사용자가 요청할 때에만 refresh가 되도록 지정한다.
- ON COMMIT: 현재 미지원
- NEVER REFRESH: 현재 미지원

> 참고: Altibase가 기본적으로 제공하는 REFERESH_MATERIALIZED_VIEW 저장 프로시저를
> 호출해서 사용자가 materialized view의 refresh를 수동으로 요청할 수 있다.
> REFERESH_MATERIALIZED_VIEW 저장 프로시저에 대한 자세한 내용은 *Stored Procedures
> Manual*의 "10장 내장 함수와 저장 프로시저"를 참고하라.

*subquery 절*

Materialized view의 쿼리문을 명시한다. 사용자가 materialized view를 생성하면, 이
절에 명시한 부질의가 실행되며, 그 결과가 materialized view에 저장된다.

#### 예제

\<질의\> employees 테이블을 베이스 테이블로 하여 이름이 mv1인 materialized
view를 생성하라. 이 때 build절과 refresh절을 지정하지 않았기 때문에, 사용자
요청으로만 refresh가 가능하며, refresh시에 complete refresh가 수행된다.

```
CREATE MATERIALIZED VIEW mv1 AS
SELECT * FROM employees;
```





### DISJOIN TABLE

#### 구문

**disjoin_table ::=**

![](media/SQL/112a655747996d5a7aa626adb1927e8a.png)



**partition_to_table_clause ::=**

![](media/SQL/cf5d8b45fc1e7f0af96650019286c30e.png)

#### 전제 조건

아래의 조건 중 하나 이상을 만족해야 테이블을 생성할 수 있다.

-   SYS 사용자이다.

-   사용자 자신의 스키마에 테이블을 생성하려면, CREATE TABLE 또는 CREATE ANY
    TABLE 시스템 권한을 가지고 있어야 한다.

-   다른 사용자의 스키마에 테이블을 생성하려면, CREATE ANY TABLE 시스템 권한을
    가지고 있어야 한다.

아래의 조건 중 하나 이상을 만족해야 테이블을 제거할 수 있다.

-   SYS 사용자이다.

-   테이블의 소유자이다.

-   DROP ANY TABLE 시스템 권한을 가진 사용자이다.

#### 설명

파티션드 테이블의 파티션이 1개 이상의 테이블로 변환된다. 파티션드 테이블은
삭제되고 논 파티션드 테이블이 생성된다. 파티션들은 각각 명시된 테이블로 변환되며
데이터는 이동된다. 테이블 스페이스 옵션을 지정하지 않으면 사용자의 기본
테이블스페이스에 새 테이블이 생성된다.

*partition_to_table*

파티션드 테이블의 파티션 이름과 변환할 테이블의 이름을 명시한다.

#### 주의 사항

DISJOIN TABLE 구문 사용시에 다음과 같은 점에 주의해야 한다.

-   대상 테이블과 생성되는 파티션드 테이블 이름에 소유자를 명시하지 않는다.

-   새로 생성된 파티션드 테이블에 관련된 메타 테이블이 새로 생성되며, 파티션드
    테이블로 변환된 대상 테이블 관련 메타 테이블은 모두 삭제된다.

-   대상 테이블과 관련된 PSM, 패키지, 뷰는 사용할 수 없다.

-   해시 파티션드 테이블은 지원하지 않는다.

-   대상 파티션드 테이블은 파티션의 속성과 제약 조건, 스키마 등을 동일하게
    갖는다.

#### 예제

\<질의\> 테이블t1의 p1, p2, p3 파티션을 각각 테이블 t2, t3, t4로 변환한다.

```
iSQL> disjoin table t1
(
  partition p1 to table t2,
  partition p2 to table t3,
  partition p3 to table t4
);
Disjoin success.
```



### DROP DATABASE 

#### 구문

**drop_database ::=**

![drop_database_image158](media/SQL/drop_database_image158.gif)

#### 전제 조건

이 구문은 SYS 사용자가 –sysdba 관리자 모드에서만 수행할 수 있으며, PROCESS 구동
단계에서만 수행할 수 있다.

#### 설명

시스템에서 데이터베이스를 삭제하는 구문이다.

*database_name*

삭제할 데이터베이스 이름을 명시한다.

이 구문이 실행되면 해당 데이터베이스가 사용하고 있던 데이터 파일과 로그 파일,
로그 앵커 파일 등이 모두 삭제된다.

#### 예제

\<질의\> mydb라는 이름의 데이터베이스를 삭제하라.

```
iSQL(sysdba)> DROP DATABASE mydb;
Checking Log Anchor files
[Ok] /home /altibase_home/logs/loganchor0 Exist.
[Ok] /home /altibase_home/logs/loganchor1 Exist.
[Ok] /home /altibase_home/logs/loganchor2 Exist.
Removing DB files
Removing Log files
Removing Log Anchor files
Drop success.
```



### DROP DATABASE LINK

데이터베이스 링크에 대한 내용은 DatabaseLink User's Manual을 참고한다.

### DROP DIRECTORY 

#### 구문

**drop_directory ::=**

![drop_directory_image160](media/SQL/drop_directory_image160.gif)

#### 전제 조건

SYS 사용자와 DROP ANY DIRECTORY 시스템 권한을 가진 사용자만이 디렉토리 객체를
삭제할 수 있다.

#### 설명

디렉토리를 제거하는 구문이다. 단, 실제 파일 시스템상의 디렉토리가 삭제되지는
않고 데이터베이스내의 디렉토리 객체만 삭제된다.

*directory_name*

제거할 디렉토리 이름을 명시한다.

#### 예제

\<질의\> 이름이 alti_dir1인 디렉토리 객체를 삭제하라.

```
iSQL> DROP DIRECTORY alti_dir1;
Drop success.
```



### DROP INDEX 

#### 구문

**drop_index ::=**

![drop_index_image161](media/SQL/drop_index_image161.gif)

#### 전제 조건

SYS 사용자, 인덱스 소유자, 테이블에 INDEX 객체 권한을 가진 사용자, DROP ANY
INDEX 시스템 권한을 가진 사용자만이 인덱스를 삭제할 수 있다.

#### 설명

데이터베이스에서 인덱스를 제거하는 구문이다.

*user_name*

제거될 인덱스 소유자 이름를 명시한다. 생략하면 Altibase는 현재 세션에 연결된
사용자의 스키마에 속한 것으로 간주한다.

*index_name*

제거할 인덱스 이름을 명시한다.

#### 예제

\<질의\> 인덱스 emp_idx1을 삭제하라.

```
iSQL> DROP INDEX emp_idx1;
Drop success.
```



### DROP JOB 

#### 구문

**drop_job ::=**

![drop_job](media/SQL/drop_job.gif)

#### 전제 조건

SYS 사용자만이 이 구문을 사용할 수 있다.

#### 설명

데이터베이스에서 JOB을 삭제한다.

*job_name*

삭제할 JOB의 이름을 명시한다.

#### 예제

\<질의\> 이름이 job1인 JOB을 제거하라.

```
iSQL> DROP JOB job1;
Drop success.
```



### DROP QUEUE 

#### 구문

**drop_queue ::=**

![drop_queue_image162](media/SQL/drop_queue_image162.gif)

#### 전제 조건

SYS 사용자, 테이블 소유자, DROP ANY TABLE 시스템 권한을 가진 사용자만이 큐를
삭제할 수 있다.

#### 설명

지정한 이름의 큐을 삭제하는 구문이다. 큐를 삭제하면 큐와 함께 생성되었던 큐
테이블, 큐 테이블의 인덱스, 및 큐 테이블의 MSGID값을 생성하는데 사용되었던
시퀀스도 삭제된다.

#### 예제

\<질의\> Q1이라는 이름을 가지는 메시지 큐와 부속 객체들을 모두 삭제하라.

```
iSQL> DROP QUEUE Q1;
```



### DROP REPLICATION 

#### 구문

**drop_replication ::=**

![drop_replication_image163](media/SQL/drop_replication_image163.gif)

#### 전제 조건

SYS 사용자만이 이중화 객체를 삭제할 수 있다.

#### 설명

이중화 객체를 제거하는 SQL 문이다.

*replication_name*

제거할 이중화 객체의 이름을 명시한다.

#### 주의 사항

실행중인 이중화 객체는 제거할 수 없다. 즉 이중화 개시(ALTER REPLICATION START)가
되어있을 경우 삭제할 수 없고, 이중화 종료(ALTER REPLICATION STOP) 후에 삭제할 수
있다.

#### 예제

\<질의\> 이중화 rep1을 삭제하라.

```
iSQL> DROP REPLICATION rep1;
```



### DROP ROLE

#### 구문

**drop_role ::=**

![drop_role](media/SQL/drop_role.gif)

#### 전제 조건

SYS 사용자와 DROP ANY ROLE 시스템 권한을 가진 사용자만이 롤(ROLE)을 삭제할 수
있다.

#### 설명

명시된 롤을 제거한다.

*role_name*

제거할 롤의 이름을 명시한다.

#### 예제

\<질의\> 이름이 alti_role인 롤을 제거한다.

```
iSQL> DROP ROLE alti_role;
Drop success.
```



### DROP SEQUENCE 

#### 구문

**drop_sequence ::=**

![drop_sequence_image164](media/SQL/drop_sequence_image164.gif)

#### 전제 조건

SYS 사용자, 시퀀스의 소유자, DROP ANY SEQUENCE 시스템 권한을 가진 사용자만이
시퀀스를 삭제할 수 있다.

#### 설명

명시된 시퀀스를 삭제하는 구문이다.

*user_name*

제거될 시퀀스의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 세션에 연결된
사용자의 스키마에 속한 것으로 간주한다.

*seq_name*

제거할 시퀀스 이름을 명시한다.

#### 예제

\<질의\> 시퀀스 seq1을 삭제하라.

```
iSQL> DROP SEQUENCE seq1;
Drop success.
```



### DROP SYNONYM 

#### 구문

**drop_synonym ::=**

![drop_synonym](media/SQL/drop_synonym.gif)

#### 전제 조건

SYS 사용자, 시노님의 소유자, DROP ANY SYNONYM 시스템 권한을 가진 사용자만이
시노님을 삭제할 수 있다.

또한, SYS 사용자와 DROP PUBLIC SYNONYM 시스템 권한을 가진 사용자만이 PUBLIC
시노님을 삭제할 수 있다.

#### 설명

명시된 시노님을 데이터베이스에서 삭제하는 구문이다.

*PUBLIC*

PUBLIC 시노님을 삭제하기 위해서는 PUBLIC을 명시해야 한다. PUBLIC을 명시하지
않으면 명시한 이름의 PRIVATE 시노님이 삭제될 것이다.

PUBLIC을 명시한 경우 user_name은 명시할 수 없다.

*user_name*

삭제할 시노님의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 세션에 연결된
사용자의 스키마에 속한 것으로 간주한다.

*synonym_name*

삭제할 시노님의 이름을 명시한다.

#### 예제

\<질의\> my_dept 시노님을 삭제하라.

```
iSQL> DROP SYNONYM my_dept;
Drop success.
```

\<질의\> PUBLIC 시노님인 dept를 삭제하라.

```
iSQL> DROP PUBLIC SYNONYM dept;
Drop success.
```



### DROP TABLE 

#### 구문

**drop_table ::=**

![](media/SQL/3b6b6558264ad2e958e72fe192ae417a.png)

#### 전제 조건

SYS 사용자, 테이블의 소유자, DROP ANY TABLE 시스템 권한을 가진 사용자만이
테이블을 삭제할 수 있다.

#### 설명

명시된 테이블과 테이블의 데이터를 데이터베이스에서 제거하는 구문이다.

테이블을 바로 제거하지 않고, 휴지통으로 옮길 경우 RECYCLEBIN_ENABLE 프로퍼티의
값을 1로 설정한다. 같은 이름의 테이블이 여러 번 DROP될 수 있으며, 휴지통의
크기를 넘을 수는 없다.

*user_name*

제거될 테이블의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 세션에 연결된
사용자의 스키마에 속한 것으로 간주한다.

*table_name*

제거될 테이블의 이름을 명시한다.

*{CASCADE \| CASCADE CONSTRAINTS}*

삭제될 테이블의 기본 키, 유니크 키를 참조하는 다른 테이블들의 참조 무결성
제약조건(referential integrity constraint)도 함께 삭제된다.

#### 예제

\<질의\> employees 테이블을 삭제하라.

```
iSQL> DROP TABLE employees;
Drop success.
```



### DROP TABLESPACE

#### 구문

**drop_tablespace ::=**

![drop_tablespace_image167](media/SQL/drop_tablespace_image167.gif)

#### 전제 조건

SYS 사용자와 DROP TABLESPACE 시스템 권한을 가진 사용자만이 테이블스페이스를
삭제할 수 있다.

#### 설명

데이터베이스에서 테이블스페이스를 제거하는 구문이다.

*tblspace_name*

제거할 테이블스페이스를 명시한다.

*INCLUDING CONTENTS*

테이블스페이스 내의 모든 내용도 삭제된다. 만약 테이블스페이스 내에 하나 이상의
객체가 존재할 경우 테이블스페이스를 삭제하려면 반드시 이 절을 명시해야 한다.
그렇지 않은 경우 Altibase는 오류를 발생시키고 DROP TABLESPACE문의 수행은
실패한다.

*AND DATAFILES*

INCLUDING CONTENTS 절과 함께 AND DATAFILES 절을 명시하면 파일 시스템에서 삭제될
테이블스페이스와 관련된 모든 파일이 삭제된다.

디스크 테이블스페이스를 삭제할 경우 디스크 테이블스페이스의 모든 데이터 파일이
파일 시스템으로부터 삭제된다.

메모리 테이블스페이스를 삭제할 경우 메모리 테이블스페이스의 모든 체크포인트
이미지 파일들이 파일 시스템으로부터 삭제된다. 그러나, 체크포인트 경로는 삭제되지
않는다.

또한 휘발성 테이블스페이스에 대해서는 AND DATAFILES 절을 사용할 수 없다.

*CASCADE CONSTRAINTS*

삭제될 테이블스페이스 내에 존재하는 테이블들의 기본 키, 유니크 키를 참조하는
다른 테이블스페이스에 존재하는 테이블들의 참조 무결성 제약조건(referential
integrity constraint)들도 함께 제거하려면 이 절을 명시해야 한다. 즉, 이런 참조
무결성 제약조건이 존재하는 상태에서 이 절을 명시하지 않고 수행하면 Altibase는
오류를 발생시키고 DROP TABLESPACE문의 수행은 실패할 것이다.

#### 제한 사항

다음 테이블스페이스는 시스템 테이블스페이스로, 사용자가 삭제할 수 없다.

-   SYS_TBS_MEM_DIC

-   SYS_TBS_MEM_DATA

-   SYS_TBS_DISK_DATA

-   SYS_TBS_DISK_UNDO

-   SYS_TBS_DISK_TEMP

#### 예제

\<질의 1\> 테이블스페이스 user_data를 제거하라.

```
iSQL> DROP TABLESPACE user_data;
Drop success.
```

\<질의 2\> 디스크 테이블스페이스 user_data의 모든 객체(object)와 데이터 파일들과
함께 테이블스페이스를 삭제하라.

```
iSQL> DROP TABLESPACE user_data INCLUDING CONTENTS AND DATAFILES;
Drop success.
```

\<질의 3\> 메모리 테이블스페이스 user_data의 모든 객체(object)와 데이터 파일들과
함께 테이블스페이스를 삭제하라.

```
iSQL> DROP TABLESPACE user_memory_tbs INCLUDING CONTENTS AND DATAFILES;
Drop success.
```

\<질의 4\> 테이블스페이스 user_data의 모든 객체(object)와 거기에 저장된 모든
테이블의 기본 키 또는 유니크 키를 참조하는 다른 테이블스페이스에 존재하는
테이블들의 모든 참조 무결성 제약조건들을 테이블스페이스와 함께 삭제하라.

```
iSQL> DROP TABLESPACE user_data INCLUDING CONTENTS CASCADE CONSTRAINTS;
Drop success.
```



### DROP TRIGGER

#### 구문

**drop_trigger ::=**

![drop_trigger_image168](media/SQL/drop_trigger_image168.gif)

#### 전제 조건

SYS 사용자, 트리거의 소유자, DROP ANY TRIGGER 시스템 권한을 가진 사용자만이
트리거를 삭제할 수 있다.

#### 설명

데이터베이스에서 명시된 트리거를 제거하는 구문이다.

*user_name*

제거될 트리거의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 사용자의 스키마
내에 속한 트리거를 제거한다.

*trigger_name*

제거될 트리거의 이름을 명시한다.

#### 예제

\<질의\> 트리거 del_trigger을 삭제하라.

```
iSQL> DROP TRIGGER del_trigger;
Drop success.
```



### DROP USER 

#### 구문

**drop_user ::=**

![drop_user_image169](media/SQL/drop_user_image169.gif)

#### 전제 조건

SYS 사용자와 DROP USER 시스템 권한을 가진 사용자만이 사용자를 삭제할 수 있다.

#### 설명

데이터베이스에서 명시된 사용자를 제거하는 구문이다.

*user_name*

제거될 사용자 이름을 명시한다.

*CASCADE*

데이터베이스 사용자 뿐만 아니라 그 사용자의 스키마에 속한 모든 객체를 삭제한다.
또한 해당 사용자 소유 테이블에 정의된 기본키 또는 유니크 키를 참조하는 다른
테이블들의 참조 무결성 제약조건(referential integrity constraint)들도 함께
삭제된다.

삭제될 사용자 스키마에 객체가 있는 경우 CASCADE를 생략하면, 에러가 반환되고
사용자 삭제 구문 실행은 실패할 것이다.

#### 예제

\<질의\> 사용자 uare1을 삭제하라.

```
iSQL> DROP USER uare1;
Drop success.
```

\<질의\> 사용자 uare4와 그것에 속한 모든 objects를 삭제하라.

```
iSQL> DROP USER uare4 CASCADE;
Drop success.
```



### DROP VIEW

#### 구문

**drop_view ::=**

![drop_view_image170](media/SQL/drop_view_image170.gif)

#### 전제 조건

SYS 사용자, 뷰의 소유자, DROP ANY VIEW 시스템 권한을 가진 사용자만이 뷰를 삭제할
수 있다.

#### 설명

데이터베이스에서 명시된 뷰를 제거하는 구문이다.

*user_name*

제거될 뷰의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 사용자의 스키마
내에 속하는 뷰를 제거한다.

*view_name*

제거될 뷰의 이름을 명시한다.

#### 예제

\<질의\> 뷰 avg_sal을 제거하라.

```
iSQL> DROP VIEW avg_sal;
Drop success.
```



### DROP MATERIALIZED VIEW

#### 구문

**drop_mview ::=**

![drop_mview](media/SQL/drop_mview.gif)

#### 전제 조건

아래의 사용자만이 이 구문으로 materialized view를 삭제할 수 있다.

-   SYS 사용자

-   Materialized view의 소유자

-   DROP ANY MATERIALIZED VIEW 시스템 권한을 가진 사용자

#### 설명

지정한 materialized view를 데이터베이스에서 제거하는 구문이다.

*user_name*

제거될 materialized view의 소유자 이름을 명시한다. 생략하면 Altibase는 현재
사용자의 스키마 내에 속하는 materialized view를 제거한다.

*mview_name*

제거될 materialized view의 이름을 명시한다.

#### 예제

\<질의\> 이름이 mv1인 materialized view를 제거하라.

```
DROP MATERIALIZED VIEW mv1;
```



### FLASHBACK TABLE

#### 구문

**flashback_table::=**

![](media/SQL/af48066754b43e83d3e54d7fe20abdae.png)

#### 전제 조건

아래의 조건 중 하나 이상을 만족해야 이 구문을 수행할 수 있다.

-   SYS 사용자이다.

-   사용자 자신의 테이블이면, CREATE TABLE 또는 CREATE ANY TABLE 시스템 권한을
    가지고 있어야 한다.

-   다른 사용자의 테이블이면, CREATE ANY TABLE 시스템 권한을 가지고 있어야 한다.

#### 설명

휴지통에 있는 테이블을 복원하는 구문이다. 동일 이름의 테이블이 휴지통에 여러 개
존재할 경우 가장 먼저 DROP된 테이블이 데이터베이스로 복원된다.

*table_name*

휴지통에서 복원될 테이블의 객체 이름을 명시한다. 테이블 이름은 삭제되기 전의
원본 테이블 이름이나 시스템에서 생성된 객체 이름도 명시할 수 있다. 단 동일한
이름의 테이블이 복수로 존재한다면, 가장 먼저 휴지통으로 DROP된 테이블부터
복원된다.

*RENAME TO table_name*

테이블을 복원할 때 새로운 이름을 명시할 수 있으며, 사용자의 스키마에 동일 이름이
있으면 다른 이름으로 변경할 수 있다.

### GRANT

#### 구문

**grant ::=**

![grant_image171](media/SQL/grant_image171.gif)

**grant_system_privilege ::=**

![grant_system_privilege](media/SQL/grant_system_privilege.gif)

**grant_object_privilege ::=**

![grant_object_privilege](media/SQL/grant_object_privilege.gif)

#### 전제 조건

SYS 사용자와 GRANT ANY PRIVILEGES 시스템 권한을 가진 사용자만이 시스템 권한을
부여할 수 있다. 또한 객체 권한은 객체의 소유자이거나 WITH GRANT OPTION으로 객체
권한을 부여받은 사용자만이 그 객체에 대한 권한을 다른 사용자에게 부여할 수 있다.

SYS 사용자와 GRANT ANY ROLE 시스템 권한을 가진 사용자만이 롤(role)에 시스템
권한을 부여할 수 있다.

#### 설명

명시된 사용자에게 데이터베이스와 객체에 접근하기 위한 권한들을 부여하는
구문이다.

권한은 시스템 권한과 객체 권한으로 분류된다.

*grant_system_privilege*

시스템 권한은 일반적으로 SYS 사용자에 의해 관리된다. SYS 사용자는 사용자들에게
특정 데이터베이스 작업을 수행하는 것을 허용하기 위해서 제한된 시스템 권한을
부여할 수 있다. 시스템 권한은 모든 스키마에 있는 객체들을 제어하는 광범위한
권한으로 볼 수 있다.

시스템 권한은 DDL문과 DCL문을 수행하기 위해서 필요하다.

grant_object_privilege

사용자가 특정 객체에 대한 권한을 부여 받으면, 사용자는 객체를 접근 및 조작할 수
있다. 객체 접근 권한은 일반적으로 객체 소유자에 의해 관리된다.

시스템 권한이 없으면, DML문을 수행을 위해서 객체 권한이 필요하다.

#### 시스템 권한 (System Privileges) 

*system_privilege*

부여될 시스템 접근 권한의 이름을 명시한다.

*role*

부여될 롤의 이름을 명시한다.

-   롤(role)은 다른 role이나 PUBLIC에게 부여할 수 없다.

-   한 사용자에게 롤을 최대 126개까지 부여할 수 있다.

-   사용자에게 롤을 부여해도 사용자에게 바로 적용되는 것이 아니다. 사용자가
    데이터베이스에 다시 접속(connect)한 후에 롤의 권한이 적용된다.

*ALL PRIVILEGES*

모든 시스템 권한을 사용자에게 부여하기 위해 사용되는 옵션이다.

*TO user*

시스템 권한을 부여할 사용자 이름을 명시한다.

*TO role*

시스템 권한을 부여할 롤(role)의 이름을 명시한다.

*TO PUBLIC*

모든 사용자에게 시스템 권한을 부여함을 명시하는 옵션이다.

##### 주의 사항

-   SYS 사용자와 GRANT ANY PRIVILEGES 권한을 가진 사용자는 모든 시스템 권한을
    다른 사용자에게 부여할 수 있다.
-   SYS 사용자는 모든 시스템 권한을 가진다.
-   시스템 권한 중 ANY 키워드는 모든 스키마에 대한 권한을 가진다. 예를 들어
    SELECT ANY TABLE 권한은 데이터베이스 내에 있는 모든 테이블을 SELECT 할 수
    있다.
-   CREATE 권한은 객체를 생성할 수 있는 권한이며, 해당 객체를 삭제하는 권한도
    포함한다.
-   CREATE TABLE 객체 권한은 테이블 뿐만 아니라 인덱스를 생성하는 권한을
    포함한다. 이 인덱스 생성 권한은 시스템 권한이 아니라 객체 권한이다.
-   새로운 사용자가 생성될 때 기본적으로 CREATE MATERIALIZED VIEW, CREATE
    LIBRARY, CREATE SESSION, CREATE TABLE, CREATE SEQUENCE, CREATE SYNONYM,
    CREATE PROCEDURE, CREATE VIEW, CREATE TRIGGER, 그리고 CREATE DATABASE LINK
    권한이 그 사용자에게 부여된다.  

다음 쿼리를 사용하면 Altibase가 지원하는 모든 시스템 권한들의 목록을 볼 수
있다.

```
iSQL> SELECT * FROM SYSTEM_.SYS_PRIVILEGES_ where PRIV_TYPE = 2;
```

Altibase는 다음과 같은 시스템 접근 권한을 지원한다.

| PrivID | System privilege  | Name                         | Purpose                                                                                                                                             |
|--------|-------------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| 1      |                   | ALL                          | 사용자에게 모든 시스템 권한을 부여한다. 단, 이 권한을 사용자에게 부여해도 ALTER DATABASE, DROP DATABASE, MANAGER TABLESPACE 권한은 부여되지 않는다. |
| 201    | DATABASE          | ALTER SYSTEM                 | Altibase 프로퍼티 설정을 동적으로 변경할 수 있다.                                                                                                   |
| 233    |                   | ALTER DATABASE               | SYS 사용자 외의 다른 사용자에게는 부여되지 않는다.                                                                                                  |
| 234    |                   | DROP DATABASE                | SYS 사용자 외의 다른 사용자에게는 부여되지 않는다.                                                                                                  |
| 202    | INDEX             | CREATE ANY INDEX             | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서도 인덱스 생성이 가능하다.                                                                       |
| 203    |                   | ALTER ANY INDEX              | 데이터베이스에 존재하는 모든 인덱스의 정의를 변경할 수 있다.                                                                                        |
| 204    |                   | DROP ANY INDEX               | 데이터베이스에 존재하는 모든 인덱스를 삭제할 수 있다.                                                                                               |
| 205    | PROCEDURE         | CREATE PROCEDURE             | 자신의 스키마 내에 저장 프로시저나 함수를 생성할 수 있다.                                                                                           |
| 206    |                   | CREATE ANY PROCEDURE         | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에 저장 프로시저나 함수를 생성할 수 있다.                                                            |
| 207    |                   | ALTER ANY PROCEDURE          | 데이터베이스에 존재하는 모든 저장 프로시저나 함수를 재컴파일 할 수 있다.                                                                            |
| 208    |                   | DROP ANY PROCEDURE           | 데이터베이스에 존재하는 모든 저장 프로시저나 함수를 삭제할 수 있다.                                                                                 |
| 209    |                   | EXECUTE ANY PROCEDURE        | 데이터베이스에 존재하는 모든 저장 프로시저나 함수를 실행할 수 있다.                                                                                 |
| 210    | SEQUENCE          | CREATE SEQUENCE              | 자신의 스키마 내에 시퀀스를 생성할 수 있다.                                                                                                         |
| 211    |                   | CREATE ANY SEQUENCE          | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서도 시퀀스 생성이 가능하다.                                                                       |
| 212    |                   | ALTER ANY SEQUENCE           | 데이터베이스에 존재하는 모든 시퀀스의 정의를 변경할 수 있다.                                                                                        |
| 213    |                   | DROP ANY SEQUENCE            | 데이터베이스에 존재하는 모든 시퀀스를 삭제할 수 있다.                                                                                               |
| 214    |                   | SELECT ANY SEQUENCE          | 데이터베이스에 존재하는 모든 시퀀스를 조회할 수 있다.                                                                                               |
| 215    | SESSION           | CREATE SESSION               | 서버에 연결할 수 있다.                                                                                                                              |
| 216    |                   | ALTER SESSION                | 자동으로 모든 사용자에게 부여된다.                                                                                                                  |
| 217    | TABLE             | CREATE TABLE                 | 자신의 스키마 내에 테이블을 생성할 수 있다.                                                                                                         |
| 218    |                   | CREATE ANY TABLE             | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서도 테이블 생성이 가능하다.                                                                       |
| 219    |                   | ALTER ANY TABLE              | 데이터베이스에 존재하는 모든 테이블에 대해서 truncate(모든 레코드 삭제)하거나 모든 테이블의 정의를 변경할 수 있다.                                  |
| 220    |                   | DELETE ANY TABLE             | 데이터베이스에 존재하는 모든 테이블의 레코드를 삭제 할 수 있다.                                                                                     |
| 221    |                   | DROP ANY TABLE               | 데이터베이스에 존재하는 모든 테이블을 삭제할 수 있다.                                                                                               |
| 222    |                   | INSERT ANY TABLE             | 데이터베이스에 존재하는 모든 테이블에 새로운 레코드를 삽입할 수 있다.                                                                               |
| 223    |                   | LOCK ANY TABLE               | 데이터베이스에 존재하는 모든 테이블에 테이블 잠금을 할 수 있다.                                                                                     |
| 224    |                   | SELECT ANY TABLE             | 데이터베이스에 존재하는 모든 테이블의 데이터를 조회할 수 있다.                                                                                      |
| 225    |                   | UPDATE ANY TABLE             | 데이터베이스에 존재하는 모든 테이블의 데이터를 변경할 수 있다.                                                                                      |
| 226    | USER              | CREATE USER                  | 새로운 사용자를 생성할 수 있다.                                                                                                                     |
| 227    |                   | ALTER USER                   | 모든 사용자의 암호를 변경할 수 있다.                                                                                                                |
| 228    |                   | DROP USER                    | 사용자를 제거할 수 있다.                                                                                                                            |
| 229    | VIEW              | CREATE VIEW                  | 자신의 스키마 내에 뷰를 생성할 수 있다.                                                                                                             |
| 230    |                   | CREATE ANY VIEW              | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서도 뷰 생성이 가능하다.                                                                           |
| 231    |                   | DROP ANY VIEW                | 데이터베이스에 존재하는 모든 뷰를 삭제 할 수 있다.                                                                                                  |
| 232    | MISCELLANEOUS     | GRANT ANY PRIVILEGES         | 모든 시스템 권한을 다른 사용자에게 부여할 수 있다.                                                                                                  |
| 235    | TABLESPACES       | CREATE TABLESPACE            | 테이블스페이스를 생성할 수 있다.                                                                                                                    |
| 236    |                   | ALTER TABLESPACE             | 테이블스페이스 정의를 변경할 수 있다.                                                                                                               |
| 237    |                   | DROP TABLESPACE              | 테이블스페이스를 삭제할 수 있다.                                                                                                                    |
| 238    |                   | MANAGE TABLESPACE            | SYS 사용자 외의 다른 사용자에게는 부여되지 않는다.                                                                                                  |
| 240    |                   | SYSDBA                       | SYS 사용자 외의 다른 사용자에게는 부여되지 않는다.                                                                                                  |
| 241    | TRIGGER           | CREATE TRIGGER               | 자신의 스키마 내에 새로운 트리거를 생성할 수 있다.                                                                                                  |
| 242    |                   | CREATE ANY TRIGGER           | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서도 트리거 생성이 가능하다.                                                                       |
| 243    |                   | ALTER ANY TRIGGER            | 데이터베이스에 존재하는 모든 트리거의 정의를 변경할 수 있다.                                                                                        |
| 244    |                   | DROP ANY TRIGGER             | 데이터베이스에 존재하는 모든 트리거를 제거할 수 있다.                                                                                               |
| 245    | SYNONYM           | CREATE SYNONYM               | 자기 소유의 시노님 (private synonym)을 생성할 수 있다.                                                                                              |
| 246    |                   | CREATE PUBLIC SYNONYM        | PUBLIC 시노님을 생성할 수 있다.                                                                                                                     |
| 247    |                   | CREATE ANY SYNONYM           | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서도 PRIVATE 시노님을 생성할 수 있다.                                                              |
| 248    |                   | DROP ANY SYNONYM             | PRIVATE 시노님을 삭제할 수 있다.                                                                                                                    |
| 249    |                   | DROP PUBLIC SYNONYM          | PUBLIC 시노님을 삭제할 수 있다.                                                                                                                     |
| 250    | DIRECTORY         | CREATE ANY DIRECTORY         | 저장프로시저 내에서 파일 제어를 위해 사용되는 디렉토리 객체를 생성할 수 있다.                                                                       |
| 251    |                   | DROP ANY DIRECTORY           | 디렉토리 객체를 삭제할 수 있다.                                                                                                                     |
| 252    | MATERIALIZED VIEW | CREATE MATERIALIZED VIEW     | 자신의 스키마 내에 새로운 MATERIALIZED VIEW를 생성할 수 있다.                                                                                       |
| 253    |                   | CREATE ANY MATERIALIZED VIEW | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에 MATERIALIZED VIEW를 생성할 수 있다.                                                               |
| 254    |                   | ALTER ANY MATERIALIZED VIEW  | 데이터베이스에 존재하는 모든 MATERIALIZED VIEW를 변경할 수 있다.                                                                                    |
| 255    |                   | DROP ANY MATERIALIZED VIEW   | 데이터베이스에 존재하는 모든 MATERIALIZED VIEW를 삭제 할 수 있다.                                                                                   |
| 256    | LIBRARY           | CREATE LIBRARY               | 자신의 스키마 내에 새로운 라이브러리 객체를 생성할 수 있다.                                                                                         |
| 257    |                   | CREATE ANY LIBRARY           | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서도 라이브러리 객체 생성이 가능하다.                                                              |
| 258    |                   | ALTER ANY LIBRARY            | 데이터베이스에 존재하는 모든 라이브러리 객체를 컴파일할 수 있다.                                                                                    |
| 259    |                   | DROP ANY LIBRARY             | 데이터베이스에 존재하는 모든 라이브러리 객체를 제거할 수 있다.                                                                                      |
| 260    | DATABASE LINK     | CREATE DATABASE LINK         | 새로운 데이터베이스 링크를 생성할 수 있다.                                                                                                          |
| 261    |                   | CREATE PUBLIC_DATABASE LINK  | PUBLIC 데이터베이스 링크를 생성할 수 있다.                                                                                                          |
| 262    |                   | DROP PUBLIC DATABASE LINK    | PUBLIC 데이터베이스 링크를 삭제할 수 있다.                                                                                                          |
| 263    | ROLE              | CREATE ROLE                  | 새로운 롤을 생성할 수 있다.                                                                                                                         |
| 264    |                   | DROP ANY ROLE                | 데이터베이스에 존재하는 모든 롤을 삭제할 수 있다.                                                                                                   |
| 265    |                   | GRANT ANY ROLE               | 모든 롤을 다른 사용자에게 부여할 수 있다.                                                                                                           |
| 266    | JOB               | CREATE ANY JOB               | 자신의 스키마 뿐 아니라 다른 사용자의 스키마 내에서 새로운 JOB을 생성할 수 있다.                                                                    |
| 268    |                   | ALTER ANY JOB                | 데이터베이스에 존재하는 모든 JOB을 변경할 수 있다.                                                                                                  |
| 267    |                   | DROP ANY JOB                 | 데이터베이스에 존재하는 모든 JOB을 삭제할 수 있다.                                                                                                  |

#### 객체 권한 (Object privileges) 

*object_privilege*

어떤 객체에 대한 특정 권한만을 부여하고자 할 때 사용되는 절이다. (이 절의
아래에 어떤 객체에 대해서 어떤 권한이 지원되는지를 [보여주는 표](#grant_tbl2)가
있다.)

*ALL [PRIVILEGES]*

객체에 대한 모든 가능한 권한을 부여하는 옵션이다.

*ON object*

어느 객체에 대해서 권한을 부여할 것인지를 명시하는 절이다. 객체에는 테이블,
시퀀스, 저장 프로시저가 있다.

*ON DIRECTORY directory_name*

권한을 부여할 대상인 저장 프로시저 내에서 사용하는 디렉토리 객체의 이름을
명시한다.

*TO user*

객체에 대한 객체 권한을 부여 받는 사용자를 명시한다.

*TO PUBLIC*

모든 사용자에게 객체 권한을 부여한다.

*TO role*

객체 권한을 부여할 롤(role)의 이름을 명시한다.

*WITH GRANT OPTION*

권한 수여자가 다른 사용자들에게 자신이 받은 객체 권한을 부여할 수 있는 옵션이다.
단 롤에 객체 권한을 부여할 때는 WITH GRANT OPTION을 사용할 수 없다.

> ##### 요약 정리
>
> -   객체의 소유자란 객체를 생성한 사용자로서, 해당 객체에 대한 모든 객체 권한을
>     가진다.
>
> -   객체 권한은 객체의 소유자이거나, WITH GRANT OPTION으로 객체 권한을 부여받은
>     사용자만이 그 객체에 대한 권한을 다른 사용자에게 부여할 수 있다.
>
> -   SYS 사용자가 객체 권한을 부여받지 못하였다면, 권한은 SYS로써 한정될 뿐 다른
>     사용자에게 권한을 부여할 수 없다.
>

다음 쿼리로 Altibase에서 지원하는 모든 객체 권한들에 대한 정보를 볼 수 있다.

```
SELECT * FROM SYSTEM_.SYS_PRIVILEGES_ where PRIV_TYPE = 1;
```

Altibase는 다음과 같은 객체 접근 권한을 지원한다.

<a name="grant_tbl2"><a/>

| Priv ID | Object privileges | Table | Sequence | PSM/ External Procedure | View | directory | External Library |
|---------|-------------------|-------|----------|-------------------------|------|-----------|------------------|
| 101     | ALTER             | O     | O        |                         |      |           |                  |
| 102     | DELETE            | O     |          |                         |      |           |                  |
| 103     | EXECUTE           |       |          | O                       |      |           | O                |
| 104     | INDEX             | O     |          |                         |      |           |                  |
| 105     | INSERT            | O     |          |                         |      |           |                  |
| 106     | REFERENCES        | O     |          |                         |      |           |                  |
| 107     | SELECT            | O     | O        |                         | O    |           |                  |
| 108     | UPDATE            | O     |          |                         |      |           |                  |
| 109     | READ              |       |          |                         |      | O         |                  |
| 110     | WRITE             |       |          |                         |      | O         |                  |

모든 사용자는 자동으로 메타 테이블에 대한 SELECT 권한을 가진다.

#### 예제

##### 시스템 접근 권한

\<질의1\> 다음은 사용자 user5에게 EXECUTE ANY PROCEDURE, SELECT ANY TABLE, ALTER
ANY SEQUENCE, INSERT ANY TABLE, SELECT ANY SEQUENCE 등의 시스템 권한을 부여하는
예제이다.

```
iSQL> CREATE TABLE seqtbl(i1 INTEGER);
Create success.
iSQL> CREATE OR REPLACE PROCEDURE proc1
AS
BEGIN
  FOR i IN 1 .. 10 LOOP
    INSERT INTO seqtbl VALUES(i);
  END LOOP;
END;
/
Create success.

iSQL> CREATE USER uare5 IDENTIFIED BY rose5;
Create success.
iSQL> GRANT EXECUTE ANY PROCEDURE, SELECT ANY TABLE TO uare5;
Grant success.
iSQL> CONNECT uare5/rose5;
Connect success.
iSQL> EXEC sys.proc1;
Execute success.
iSQL> SELECT * FROM sys.seqtbl;
SEQTBL.I1   
--------------
1           
2           
3           
4           
5           
6           
7           
8           
9           
10          
10 rows selected.

iSQL> CONNECT sys/manager;
Connect success.
iSQL> CREATE SEQUENCE seq1
  START WITH 13
  INCREMENT BY 3
  MINVALUE 0 NOMAXVALUE;
Create success.
iSQL> INSERT INTO seqtbl VALUES(seq1.NEXTVAL);
1 row inserted.
iSQL> INSERT INTO seqtbl VALUES(seq1.NEXTVAL);
1 row inserted.
iSQL> SELECT * FROM seqtbl;
SEQTBL.I1   
--------------
1           
2           
3           
4           
5           
6           
7           
8           
9           
10          
13          
16          
12 rows selected.

iSQL> GRANT ALTER ANY SEQUENCE, INSERT ANY TABLE, SELECT ANY SEQUENCE TO uare5;
Grant success.
iSQL> CONNECT uare5/rose5;
Connect success.	
iSQL> ALTER SEQUENCE sys.seq1
  INCREMENT BY 50
  MAXVALUE 100
  CYCLE;
Alter success.

iSQL> INSERT INTO sys.seqtbl VALUES(sys.seq1.NEXTVAL);
1 row inserted.
iSQL> INSERT INTO sys.seqtbl VALUES(sys.seq1.NEXTVAL);
1 row inserted.
iSQL> INSERT INTO sys.seqtbl VALUES(sys.seq1.NEXTVAL);
1 row inserted.
iSQL> INSERT INTO sys.seqtbl VALUES(sys.seq1.NEXTVAL);
1 row inserted.
iSQL> SELECT * FROM sys.seqtbl;
SEQTBL.I1   
--------------
1           
2           
3           
4           
5           
6           
7           
8           
9           
10          
13          
16          
66          
0           
50          
100         
16 rows selected.
```

\<질의 2\> 이름이 alti_role인 롤을 생성한 후, 롤에게 create user와 drop user
등의 시스템 권한을 부여한다.

```
iSQL> create role alti_role;
Create success.
iSQL> grant create user, drop user to alti_role;
Grant success.
iSQL> create user user01 identified by user01;
Create success.
iSQL> grant alti_role to user01;
Grant success.
iSQL> connect user01/user01
Connect success.
iSQL> create user user02 identified by user02;
Create success.
iSQL> drop user user02;
Drop success.
```



##### 객체 권한

\<질의1\> 사용자 uare6가 WITH GRANT OPTION으로 employees 테이블에 대한 SELECT와
DELETE 객체 권한을 부여 받은 후, 같은 권한을 다른 사용자 uare7과 uare8에게
부여한다.

```
iSQL> CREATE USER uare6 IDENTIFIED BY rose6;
Create success.
iSQL> GRANT CREATE USER TO uare6;
Grant success.
iSQL> @schema.sql
iSQL> GRANT SELECT, DELETE ON employees TO uare6 WITH GRANT OPTION;
Grant success.
iSQL> CONNECT uare6/rose6;
Connect success.
iSQL> CREATE USER uare7 IDENTIFIED BY rose7;
Create success.
iSQL> GRANT SELECT, DELETE ON sys.employees TO uare7;
Grant success.
iSQL> CONNECT uare7/rose7;
Connect success.
iSQL> DELETE FROM SYS.employees WHERE eno = 12;
1 row deleted.
iSQL> SELECT eno, e_lastname FROM sys.employees WHERE eno = 12;
ENO         E_LASTNAME                 
-------------------------------------
No rows selected.
iSQL> CONNECT sys/manager;
Connect success.
iSQL> CREATE USER uare8 IDENTIFIED BY rose8;
Create success.
iSQL> CONNECT uare6/rose6;
Connect success.
iSQL> GRANT SELECT, DELETE ON sys.employees TO uare8;
Grant success.
```

WITH GRANT OPTION 으로 객체권한을 부여받은 사용자 uare6는 자신이 생성한 사용자
uare7 뿐만 아니라 원래의 권한 부여자(SYS)가 생성한 사용자 uare8에게도 객체
권한을 부여할 수 있다.

```
iSQL> CONNECT uare8/rose8;
Connect success.
iSQL> DELETE FROM sys.employees WHERE eno = 13;
1 row deleted.

iSQL> SELECT eno, e_lastname FROM sys.employees WHERE eno = 13;
ENO         E_LASTNAME                 
-------------------------------------
No rows selected.
```

\<질의 2\> 다음은 사용자에게 시스템 권한, 객체 권한을 부여한 후 각각의 권한을
해제하는 예제이다.

1. SYS 사용자가 uare9에게 모든 시스템 권한을 부여한다.

   ```
   iSQL> CONNECT sys/manager;
   Connect success.
   iSQL> CREATE TABLE book(
     isbn CHAR(10) PRIMARY KEY,
     title VARCHAR(50),
     author VARCHAR(30),
     edition INTEGER DEFAULT 1,
     publishingyear INTEGER,
     price NUMBER(10,2),
     pubcode CHAR(4));
   Create success.
   iSQL> CREATE TABLE inventory(
     subscriptionid CHAR(10) PRIMARY KEY,
     storecode CHAR(4),
     purchasedate DATE,
     quantity INTEGER,
     paid CHAR(1));
   Create success.
   
   iSQL> CREATE USER uare9 IDENTIFIED BY rose9;
   Create success.
   iSQL> GRANT ALL PRIVILEGES TO uare9;
   Grant success.
   ```


2. SYS는 사용자uare9에게 객체 book에 대한 REFERENCES 권한을 WITH GRANT OPTION
  으로 부여한다.

  ```
  iSQL> GRANT REFERENCES ON book TO uare9 WITH GRANT OPTION;
  Grant success.
  ```

  사용자uare9은 SYS로부터 객체 book에 대한 REFERENCES 권한을 WITH GRANT OPTION
  으로 부여 받았기 때문에, uare9은 다른 사용자(uare10)에게 객체 book에 대해
  REFERENCES 객체 권한을 부여할 수 있다.

3. uare9이 SYS의 객체인 book 테이블에 데이터를 입력한다.

   ```
   iSQL> CONNECT uare9/rose9;
   Connect success.
   
   iSQL> INSERT INTO sys.book VALUES ('0070521824', 'Software Engineering', 'Roger S. Pressman', 4, 1982, 100000, 'CHAU');
   1 row inserted.
   iSQL> INSERT INTO sys.book VALUES ('0137378424', 'Database Processing', 'David M. Kroenke', 6, 1972, 80000, 'PREN');
   1 row inserted.
   ```



   uare9이 SYS의 객체인 inventory 테이블에 데이터를 입력한다.

   ```
   iSQL> INSERT INTO sys.inventory VALUES('BORD000002', 'BORD', '12-Jun-2003', 6, 'N');
   iSQL> INSERT INTO sys.inventory VALUES('MICR000001', 'MICR', '07-Jun-2003', 7, 'N');
   1 row inserted.
   ```




4. uare9이 SYS의 객체인 book 테이블을 조회한다.

   ```
   iSQL> SELECT * FROM sys.book;
   BOOK.ISBN   BOOK.TITLE                                          
   ------------------------------------------------
   BOOK.AUTHOR                     BOOK.EDITION BOOK.PUBLISHINGYEAR BOOK.PRICE  
   ------------------------------------------------
   BOOK.PUBCODE  
   ----------------
   0070521824  Software Engineering                                
   Roger S. Pressman               4           1982        100000      
   CHAU  
   0137378424  Database Processing                                 
   David M. Kroenke                6           1972        80000       
   PREN  
   2 rows selected.
   ```



   uare9이 SYS의 객체인 inventory 테이블을 조회한다.

   ```
   iSQL> SELECT * FROM sys.inventory;
   INVENTORY.SUBSCRIPTIONID  INVENTORY.STORECODE  INVENTORY.PURCHASEDATE 
   ------------------------------------------------
   INVENTORY.QUANTITY INVENTORY.PAID  
   --------------------------------------
   BORD000002  BORD  2003/06/12 00:00:00  
   6           N  
   MICR000001  MICR  2003/06/07 00:00:00  
   7           N  
   2 rows selected.
   
   iSQL> CREATE TABLE book(
     isbn CHAR(10) PRIMARY KEY,
     title VARCHAR(50),
     author VARCHAR(30),
     edition INTEGER DEFAULT 1,
     publishingyear INTEGER,
     price NUMBER(10,2),
     pubcode CHAR(4));
   Create success.
   
   iSQL> CREATE TABLE inventory(
     subscriptionid CHAR(10) PRIMARY KEY,
     isbn CHAR(10) CONSTRAINT fk_isbn REFERENCES book(isbn), 
     storecode CHAR(4),
     purchasedate DATE,
     quantity INTEGER,
     paid CHAR(1));
   Create success.
   ```

5. uare9은 SYS로부터 ALL PRIVILEGES를 부여 받았으므로 다른 사용자를 생성할 수
  있다.

  ```
  iSQL> CREATE USER uare10 IDENTIFIED BY rose10;
  Create success.
  ```

6. SYS는 uare9에게 REFERENCES 권한을 WITH GRANT OPTION으로 부여했기 때문에,
  uare9는 다른 사용자(uare10)에게 이 권한을 부여할 수 있다.

  ```
  iSQL> GRANT REFERENCES ON sys.book TO uare10;
  Grant success.
  ```


7. GRANT ANY PRIVILEGES를 부여 받은 uare9이 다른 사용자(uare10)에게 시스템
  권한을 부여한다.



  ```
  iSQL> GRANT ALTER ANY TABLE, INSERT ANY TABLE, SELECT ANY TABLE, DELETE ANY
  TABLE TO uare10;
  Grant success.
  ```


8. 사용자 uare10은 ALTER ANY TABLE과 REFERENCE 권한이 있기 때문에, 다른 사용자
  소유의 테이블에 제약조건을 추가할 수 있다.

  ```
  iSQL> CONNECT uare10/rose10;
  Connect success.
  iSQL> ALTER TABLE sys.inventory
    ADD COLUMN (isbn CHAR(10) CONSTRAINT fk_isbn REFERENCES sys.book(isbn));
  Alter success.
  ```




9. 사용자 uare10은 INSERT ANY TABLE 권한이 있기 때문에, 사용자 uare9가 소유한
  테이블에 데이터를 입력할 수 있다.

  ```
  iSQL> INSERT INTO uare9.book VALUES('0471316156', 'JAVA and CORBA', 'Robert Orfali', 2, 1998, 50000, 'PREN');
  1 row inserted.
  iSQL> INSERT INTO uare9.inventory VALUES('TOWE000001', '0471316156', 'TOWE', '01-Jun-2003', 5, 'N');
  1 row inserted.
  ```



  사용자 uare10은 INSERT ANY TABLE 권한이 있기 때문에, SYS소유의 테이블에 데이터를
  입력할 수 있다.

  ```
  iSQL> INSERT INTO sys.book VALUES('053494566X', 'Working Classes', 'Robert Orfali', 1, 1999, 80000, 'WILE');
  1 row inserted.
  iSQL> INSERT INTO sys.inventory VALUES('MICR000005', 'WILE', '28-JUN-1999', 8, 'N', '053494566X');
  1 row inserted.
  ```


10. 사용자 uare10은 SELECT ANY TABLE 권한이 있기 때문에, uare9소유의 테이블을
    조회할 수 있다.

    ```
    iSQL> SELECT * FROM uare9.book;
    BOOK.ISBN   BOOK.TITLE                                          
    ------------------------------------------------
    BOOK.AUTHOR                     BOOK.EDITION BOOK.PUBLISHINGYEAR BOOK.PRICE  
    ------------------------------------------------
    BOOK.PUBCODE  
    ----------------
    0471316156  JAVA and CORBA                                      
    Robert Orfali                   2           1998        50000       
    PREN  
    1 row selected.
    iSQL> SELECT * FROM uare9.inventory;
    INVENTORY.SUBSCRIPTIONID  INVENTORY.ISBN  INVENTORY.STORECODE  
    ------------------------------------------------
    INVENTORY.PURCHASEDATE INVENTORY.QUANTITY INVENTORY.PAID  
    ------------------------------------------------
    TOWE000001  0471316156  TOWE  
    2003/06/01 00:00:00  5           N  
    1 row selected.
    ```



    사용자 uare10은 SELECT ANY TABLE 권한이 있기 때문에, SYS소유의 테이블을 조회할
    수 있다.

    ```
    iSQL> SELECT * FROM sys.book;
    BOOK.ISBN   BOOK.TITLE                                          
    ------------------------------------------------
    BOOK.AUTHOR                     BOOK.EDITION BOOK.PUBLISHINGYEAR BOOK.PRICE  
    ------------------------------------------------
    BOOK.PUBCODE  
    ----------------
    0070521824  Software Engineering                                
    Roger S. Pressman               4           1982        100000      
    CHAU  
    0137378424  Database Processing                                 
    David M. Kroenke                6           1972        80000       
    PREN  
    053494566X  Working Classes                                     
    Robert Orfali                   1           1999        80000       
    WILE  
    3 rows selected.
    iSQL> SELECT * FROM sys.inventory;
    INVENTORY.SUBSCRIPTIONID  INVENTORY.STORECODE  INVENTORY.PURCHASEDATE 
    ------------------------------------------------
    INVENTORY.QUANTITY INVENTORY.PAID  INVENTORY.ISBN  
    ------------------------------------------------
    BORD000002  BORD  2003/06/12 00:00:00  
    6           N              
    MICR000001  MICR  2003/06/07 00:00:00  
    7           N              
    MICR000005  WILE  1999/06/28 00:00:00  
    8           N  053494566X  
    3 rows selected.
    ```


11. 사용자 uare10은 DELETE ANY TABLE 권한이 있기 때문에, SYS와 uare9소유의
    테이블의 데이터를 삭제할 수 있다.

    ```
    iSQL> DELETE FROM uare9.inventory WHERE subscriptionid = 'TOWE000001';
    1 row deleted.
    iSQL> SELECT * FROM uare9.inventory;
    INVENTORY.SUBSCRIPTIONID  INVENTORY.ISBN  INVENTORY.STORECODE  
    ------------------------------------------------
    INVENTORY.PURCHASEDATE INVENTORY.QUANTITY INVENTORY.PAID  
    ------------------------------------------------
    No rows selected.
    
    iSQL> DELETE FROM sys.inventory WHERE subscriptionid = 'MICR000005';
    1 row deleted.
    iSQL> SELECT * FROM sys.inventory;
    INVENTORY.SUBSCRIPTIONID  INVENTORY.STORECODE  INVENTORY.PURCHASEDATE 
    ------------------------------------------------
    INVENTORY.QUANTITY INVENTORY.PAID  INVENTORY.ISBN  
    ------------------------------------------------
    BORD000002  BORD  2003/06/12 00:00:00  
    6           N              
    MICR000001  MICR  2003/06/07 00:00:00  
    7           N              
    2 rows selected.
    
    ```




12. 사용자 uare9이 REVOKE ALL 구문을 사용하지 않고 uare10으로부터 모든 권한을
    해제한다.

    ```
    iSQL> CONNECT uare9/rose9;
    Connect success.
    iSQL> REVOKE ALTER ANY TABLE, INSERT ANY TABLE, SELECT ANY TABLE, DELETE ANY TABLE FROM uare10;
    Revoke success.
    ```




13. 사용자 uare10의 REFERENCES 권한과 함께 관련된 참조 무결성
    제약조건(referential integrity constraints)도 같이 삭제한다.

    ```
    iSQL> REVOKE REFERENCES ON sys.book FROM uare10 CASCADE CONSTRAINTS;
    Revoke success.
    ```




14. 사용자 uare9의 모든 시스템 권한을 해제한다.

    ```
    iSQL> CONNECT sys/manager;
    Connect success.
    iSQL> REVOKE ALL PRIVILEGES FROM uare9;
    Revoke success.
    ```


15. 사용자 uare9의 GRANT ANY PRIVILEGES 권한을 해제한다.

    ```
    iSQL> REVOKE GRANT ANY PRIVILEGES FROM uare9;
    Revoke success.
    ```


16. 사용자 uare9의 REFERENCES 권한을 해제한다.

iSQL\> REVOKE REFERENCES ON book FROM uare9;

Revoke success.

\<질의 3\> user01의 T1 테이블에 대한 SELECT, UPDATE, INSERT, DELETE 객체 권한을
alti_role 롤에 부여한다. 그리고 alti_role 롤을 다른 사용자 user02에게 부여한다.

iSQL\> create role alti_role;

Create success.

iSQL\> create user user01 identified by user01;

Create success.

iSQL\> create user user02 identified by user02;

Create success.

iSQL\> connect user01/user01

Connect success.

iSQL\> create table t1 (i1 integer);

Create success.

iSQL\> grant select,insert,update,delete on t1 to alti_role;

Grant success.

iSQL\> connect sys/manager

Connect success.

iSQL\> grant alti_role to user02;

Grant success.

iSQL\> connect user02/user02;

Connect success.

iSQL\> insert into user01.t1 values (1);

1 row inserted.

iSQL\> insert into user01.t1 values (2);

1 row inserted.

iSQL\> select \* from user01.t1;

T1.I1

\--------------

1

2

2 rows selected.

iSQL\> update user01.t1 set i1=3 where i1=1;

1 row updated.

iSQL\> select \* from user01.t1;

T1.I1

\--------------

2

3

2 rows selected.

iSQL\> delete from user01.t1 where i1=2;

1 row deleted.

iSQL\> select \* from user01.t1;

T1.I1

\--------------

3

1 row selected.

### PURGE TABLE 

#### 구문

purge_table::=

![](media/SQL/bdce75dd2f142620aa1120b6035f7c67.png)

#### 전제 조건

SYS 사용자, 테이블의 소유자, DROP ANY TABLE 시스템 권한을 가진 사용자만이 이
구문을 수행할 수 있다.

#### 설명

명시한 테이블이 휴지통에서 제거되는 구문이다. 동일 이름의 테이블이 휴지통에 여러
개 존재할 경우 가장 먼저 DROP된 테이블이 데이터베이스에서 삭제된다.

user_name

테이블의 소유자 이름을 명시한다.

table_name

휴지통에서 제거할 테이블의 이름을 명시한다. 테이블의 이름은 DROP 되기 전의
테이블의 이름이거나 휴지통으로 옮겨지면서 시스템에서 부여된 객체의 이름을 명시할
수 있다.

#### 예제

\<질의\> DROP이 수행된 테이블 t1을 휴지통에서 비운다.

iSQL\> alter session set recyclebin_enable = 1;

Alter success.

iSQL\> create table t1 (i1 integer);

Create success.

iSQL\> drop table t1;

Drop success.

iSQL\> purge table t1;

Purge success.

### RENAME TABLE 

#### 구문

rename ::=

#### 전제 조건

SYS 사용자, 테이블이 속한 스키마의 소유자, 테이블에 ALTER 객체 권한을 가진
사용자, 또는 ALTER ANY TABLE 시스템 권한을 가진 사용자만이 테이블 이름을 변경할
수 있다.

#### 설명

명시된 테이블의 이름을 새로운 이름으로 변경한다. 테이블의 이름만 변경되고 그
안에 저장된 데이터는 유지된다.

user_name

이름이 변경될 테이블의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 세션에
연결된 사용자의 스키마에 속한 것으로 간주한다.

old_name

테이블의 현재 이름을 명시한다.

new_name

테이블에 주어질 새로운 이름을 명시한다.

#### 주의 사항

이중화 대상 테이블일 경우 테이블의 이름을 변경할 수 없다.

#### 예제

\<질의\> 테이블 employees의 이름을 emp1으로 변경하라.

iSQL\> RENAME employees TO emp1;

Rename success.

또는

iSQL\> ALTER TABLE employees

RENAME TO emp1;

Alter success.

### REVOKE 

#### 구문

revoke ::=

revoke_system_privilege ::=

revoke_object_privilege ::=

#### 전제 조건

SYS 사용자와 원래 그 권한을 부여한 사용자만이 해당 권한을 해제할 수 있다.

#### 설명

REVOKE 구문은 명시된 사용자가 가진 시스템 권한 또는 특정 객체에 대한 객체 권한
또는 롤을 해제한다. 또는 롤에 부여된 시스템 권한 또는 객체 권한을 해제한다.

시스템 및 객체 접근 권한, 롤을 해제하려면 GRANT 명령으로 직접 부여되었던
권한들에 대해서만 해제할 수 있다.

##### 시스템 접근 권한 (System privilege)

role

해제할 롤을 명시한다.

system_privilege

해제할 시스템 권한을 명시하는 절이다. 시스템 권한의 목록은 GRANT구문의 설명을
참고한다.

ALL PRIVILEGES

이 REVOKE 문을 실행하는 사용자에 의해서 부여된 모든 시스템 권한을 해제하는
옵션이다.

ALL PRIVILEGES 옵션으로 부여된 시스템 권한은 ALL PRIVILEGES 옵션을 사용해서
해제하거나 각각의 권한을 따로따로 해제해도 된다.

FROM user

시스템 권한을 해제할 사용자를 명시한다.

FROM role

어느 롤에서 시스템 권한을 해제할지 명시한다.

FROM PUBLIC

모든 사용자로부터 시스템 권한을 해제하는 옵션이다.

Note: PUBLIC옵션으로 부여된 시스템 권한은 PUBLIC옵션으로 해제할 수 있다.

##### 객체 권한 (Object privilege)

role

해제할 롤을 명시한다.

object_privilege

해제할 객체 권한을 명시하는 절이다. 객체 권한의 목록은 GRANT구문의 설명을
참고한다.

ALL [PRIVILEGES]

이 REVOKE 문을 실행하는 사용자에 의해서 부여된 모든 객체 권한을 해제하는
옵션이다.

ALL PRIVILEGES 옵션으로 권한을 해제하면, 사용자에게 부여된 모든 객체 권한이
해제된다. 즉, ALL [PRIVILEGES] 옵션을 사용하지 않고 부여된 객체 권한도 해제된다.
예을 들어, 다음 구문으로 부여된 객체 권한은:

GRANT SELECT ON *object* TO *user*;

다음 방법으로 명시적으로 해제될 수 있다:

REVOKE SELECT ON *object* FROM *user*;

또한, 다음 구문을 사용하면 모든 다른 권한도 함께 해제된다:

REVOKE ALL ON *object* FROM *user*;

ON object

어느 객체(테이블, 시퀀스, 저장 프로시저 등)에 대한 권한을 해제할지를 명시하는
절이다.

ON DIRECTORY directory_name

어느 디렉토리 객체에 대한 객체 권한을 해제할지를 명시하는 절이다.

FROM user

객체 권한을 해제할 사용자를 명시하는 절이다.

FROM role

어느 롤에서 객체 권한을 해제할지 명시한다.

FROM PUBLIC

모든 사용자로부터 객체 권한을 해제하는 옵션이다.

CASCADE CONSTRAINTS

REFERENCES 권한 또는 ALL [PRIVILEGS]를 사용해서 해제할 때 사용할 수 있는
옵션이다. 이 옵션을 사용해서 사용자의 권한을 해제하면 관련된 모든 참조 무결성
제약조건(referential integrity constraints)도 함께 삭제된다.

#### 예제

\<질의\> 객체 권한을 해제하라

iSQL\> CONNECT uare6/rose6;

Connect success.

iSQL\> REVOKE SELECT, DELETE ON sys.employees

FROM uare7, uare8;

Revoke success.

iSQL\> CONNECT uare7/rose7;

Connect success.

iSQL\> SELECT eno, e_lastname FROM sys.employees WHERE eno = 15;

[ERR-311B1: The user must have the SELECT_ANY_TABLE privilege(s) to execute this
statement.]

employees 테이블에 대한 SELECT와 DELETE 권한 해제 후, 그 테이블에 SELECT 문을
실행하면 오류 메시지를 볼 수 있다.

\<질의 2\> 롤에 부여된 create user, drop user의 시스템 권한 중에서 create user
권한을 해제한다.

iSQL\> create role alti_role;

Create success.

iSQL\> grant create user, drop user to alti_role;

Grant success.

iSQL\> create user user01 identified by user01;

Create success.

iSQL\> grant alti_role to user01;

Grant success.

iSQL\> connect user01/user01

Connect success.

iSQL\> create user user02 identified by user02;

Create success.

iSQL\> drop user user02;

Drop success.

iSQL\> connect sys/manager

Connect success.

iSQL\> revoke create user from alti_role;

Revoke success.

iSQL\> connect user01/user01

Connect success.

iSQL\> create user user02 identified by user02;

[ERR-311B1 : The user must have CREATE_USER privilege(s) to execute this
statement.]

\<질의 3\> alti_role 롤에서 사용자 user01의 테이블 t1에 대한 DELETE 객체 권한을
해제한다.

iSQL\> create role alti_role;

Create success.

iSQL\> create user user01 identified by user01;

Create success.

iSQL\> create user user02 identified by user02;

Create success.

iSQL\> connect user01/user01

Connect success.

iSQL\> create table t1 (i1 integer);

Create success.

iSQL\> grant select,insert,update,delete on t1 to alti_role;

Grant success.

iSQL\> connect sys/manager

Connect success.

iSQL\> grant alti_role to user02;

Grant success.

iSQL\> connect user02/user02;

Connect success.

iSQL\> insert into user01.t1 values (1);

1 row inserted.

iSQL\> insert into user01.t1 values (2);

1 row inserted.

iSQL\> select \* from user01.t1;

I1

\--------------

1

2

2 rows selected.

iSQL\> update user01.t1 set i1=3 where i1=1;

1 row updated.

iSQL\> select \* from user01.t1;

I1

\--------------

2

3

2 rows selected.

iSQL\> delete from user01.t1 where i1=2;

1 row deleted.

iSQL\> select \* from user01.t1;

I1

\--------------

3

1 row selected.

iSQL\> connect user01/user01

Connect success.

iSQL\> revoke delete on t1 from alti_role;

Revoke success.

iSQL\> connect user02/user02

Connect success.

iSQL\> delete from user01.t1 where i1=3;

[ERR-311B1 : The user must have DELETE_ANY_TABLE privilege(s) to execute this
statement.]

### TRUNCATE TABLE 

#### 구문

truncate ::=

#### 전제 조건

SYS 사용자, 테이블이 속한 스키마의 소유자, 테이블에 ALTER 객체 권한을 가진
사용자, 또는 ALTER ANY TABLE 시스템 권한을 가진 사용자만이 테이블 이름을 변경할
수 있다.

#### 설명

명시된 테이블의 모든 레코드를 삭제하는 구문이다.

user_name

레코드가 삭제될 테이블의 소유자 이름을 명시한다. 생략하면 Altibase는 현재 세션에
연결된 사용자의 스키마에 속한 것으로 간주한다.

tbl_name

레코드가 삭제될 테이블 이름을 명시한다.

*table_name* 에는 큐 테이블 명을 지정하여 ENQUE된 메시지를 한꺼번에 삭제할 수
있다.

#### TRUNCATE vs. DELETE

TRUNCATE 문을 수행한 경우는 해당 테이블에 할당된 모든 페이지가 데이터베이스에
free page로 반납된다. 따라서 이 페이지들은 다른 테이블에 의해 사용될 수 있다.
그러나 DELETE 문을 수행하여 해당 테이블의 모든 레코드를 삭제한 경우는 free
page가 생기더라도 데이터베이스에 다시 반납되지 않고 해당 테이블 내에 유지되기
때문에 메모리 사용량이 줄지 않는다.

TRUNCATE 구문은 DDL구문이므로 이 구문을 성공적으로 수행한 후에는 rollback이
불가능하다.

#### 주의 사항

레코드의 삭제가 성공적으로 수행되었다면 삭제된 레코드는 복구될 수 없다. 그러나
수행 완료 전에 오류가 발생한 경우나 서버가 죽은 경우엔 롤백이 가능하다.

#### 예제

\<질의\> 테이블 employees의 모든 데이터를 삭제하라.

iSQL\> TRUNCATE TABLE employee;

Truncate success.

데이터 조작어
-------------

이 장에서는 데이터 조작에 사용되는 DML 구문에 대해서 상세히 설명한다.

### DELETE 

#### 구문

delete ::=

[hints ::=](#hints_diagram)

from_clause ::=

where_clause ::=

returning_clause ::=

limit_clause ::=

#### 전제 조건

SYS 사용자, 테이블 소유자, DELETE ANY TABLE 시스템 권한을 가진 사용자 및
테이블에 대한 DELETE 객체 권한을 가진 사용자만이 이 구문으로 해당 테이블의
레코드를 삭제할 수 있다.

뷰의 레코드를 삭제할 경우, 사용자는 베이스 테이블에 대해 위와 동일한 권한을
가져야 한다.

#### 설명

조건을 만족하는 레코드를 해당 테이블에서 삭제하는 구문이다. 또한 이 구문으로
특정 파티션에 있는 데이터를 삭제할 수도 있다.

WHERE 절은 SELECT구문의 WHERE 절과 동일하다. WHERE 절을 생략하면 테이블의 모든
데이터가 삭제된다.

user_name

레코드를 삭제할 테이블의 소유자 이름을 명시한다. 생략하면 Altibase는 테이블이
현재 세션에 연결된 사용자의 스키마에 속한 것으로 간주한다.

tbl_name

삭제될 레코드를 포함한 테이블 이름을 명시한다.

view_name

레코드가 삭제될 뷰의 이름을 명시한다.

subquery

레코드를 삭제하려는 뷰를 서브쿼리로 명시한다.

returning_clause

returning 절은 DML 문에 의해 영향을 받은 레코드를 조회한다.

expr

각 expr는 DML 문에 의해 영향을 받는 칼럼의 이름이거나 칼럼 타입과 호환되는
데이터 표현식이어야 한다.

INTO

INTO 절은 변경된 레코드의 값들이 각 값에 대응하는 variable_name 변수로 저장될
것을 지시한다.

variable_name

각 variable_name은 조회된 expr 값을 저장할 호스트 변수 또는 PSM 변수이다. RECORD
타입의 변수를 사용하는 경우를 제외하면, 변수의 개수는 expr 리스트의 expr 개수와
동일해야 한다.

호스트 변수 또는 PSM 변수의 타입은 대응하는 expr의 타입과 호환되어야 한다.

참고: iSQL에서는 변수 이름 앞에 ':'을 붙여 사용해야 한다.

Returning 절의 제약 사항:

-   UPDATE, DELETE, 및 INSERT문의 경우, 각 expr에는 aggregate 함수가 올 수 없다.

-   이 절은 테이블에 대해서만 사용할 수 있다.

-   이 절로 LOB 타입을 조회할 수 없다.

-   expr에 별칭(alias) 또는 부질의(subquery)가 올 수 없다.

-   expr에 시퀀스를 사용할 수 없다.

참고: PSM 내에서 BULK COLLECT 절을 사용해서 한꺼번에 여러 행을 collection 변수로
반환할 수 있다. 이에 대한 자세한 내용은 *Stored Procedures Manual*을 참고하라.

#### HINTS 옵션

힌트의 문법과 자세한 설명은 "[힌트 구문](#hint_syntax)"과 "[힌트
목록](#힌트-목록)"을 참고하기 바란다.

#### 예제

##### 단순 데이터 삭제

\<질의\> 테이블의 모든 데이터를 삭제하라.

DELETE FROM orders;

\<질의\> T1 테이블의 P2 파티션의 모든 데이터를 삭제한다

DELETE FROM T1 PARTITION (P2);

\<질의\> 직원 ’William’이 받은 주문들을 삭제한다.

DELETE

FROM orders

WHERE eno = (SELECT eno FROM employees

WHERE e_firstname = 'William');

##### 조인 뷰의 데이터 삭제

\<질의\> employees와 departments 테이블의 조인 뷰를 생성한 후, 'BUSINESS DEPT'
부서에 속한 사원을 삭제한다. employees 테이블의 데이터 삭제 전후 행 개수를
비교하면, employees 테이블의 데이터가 삭제된 것을 확인할 수 있다.

iSQL\> CREATE VIEW simple_emp AS

SELECT e.eno, e.e_lastname, e.salary, d.dname

FROM employees e, departments d

WHERE e.dno = d.dno;

Create success.

iSQL\> select \* from simple_emp;

ENO E_LASTNAME SALARY DNAME

\-----------------------------------------------------------------------------------

3 Kobain 2000 RESEARCH DEVELOPMENT DEPT 1

16 Chen 2300 RESEARCH DEVELOPMENT DEPT 1

6 Momoi 1700 RESEARCH DEVELOPMENT DEPT 2

13 Jones 980 RESEARCH DEVELOPMENT DEPT 2

10 Bae 4000 SOLUTION DEVELOPMENT DEPT

11 Liu 2750 SOLUTION DEVELOPMENT DEPT

14 Miura 2003 SOLUTION DEVELOPMENT DEPT

15 Davenport 1000 SOLUTION DEVELOPMENT DEPT

17 Fubuki 1400 QUALITY ASSURANCE DEPT

4 Foster 1800 CUSTOMERS SUPPORT DEPT

1 Moon PRESALES DEPT

5 Ghorbani 2500 PRESALES DEPT

8 Wang MARKETING DEPT

9 Diaz 1200 MARKETING DEPT

18 Huxley 1900 MARKETING DEPT

7 Fleischer 500 BUSINESS DEPT

12 Hammond 1890 BUSINESS DEPT

19 Marquez 1800 BUSINESS DEPT

20 Blake BUSINESS DEPT

19 rows selected.

iSQL\> select count(\*) from employees;

COUNT

\-----------------------

20

1 row selected.

iSQL\> DELETE FROM simple_emp WHERE dname='BUSINESS DEPT';

4 rows deleted.

iSQL\> select count(\*) from employees;

COUNT

\-----------------------

16

1 row selected.

##### Returing 절을 사용한 삭제

\<질의\> 삭제된 행의 값을 출력 바인드 변수인 :v1, :v2로 반환하도록 한다.

iSQL\> create table employees ( eno integer, ename varchar(20));

Create success.

iSQL\> var v1 output integer;

iSQL\> var v2 output varchar(30);

iSQL\> insert into employees values (1, 'jake');

iSQL\> insert into employees values (2, 'nikita');

iSQL\> insert into employees values (3, 'dana');

iSQL\> prepare delete from employees where eno=2 return eno, ename into :v1,
:v2;

1 row deleted.

iSQL\> print var

[ HOST VARIABLE ]

\-------------------------------------------------------

NAME TYPE VALUE

\-------------------------------------------------------

V1 INTEGER 2

V2 VARCHAR(30) nikita

### INSERT 

#### 구문

insert ::=

![](media/SQL/a45155edc3025bff4fdd2260e889e4ab.png)

[hints ::=](#hints_diagram),

single_table_insert ::=

[values_clause ::=](#values_clause), [returning_clause ::=](#returning_clause),
[subquery ::=](#subquery)

table_clause ::=

[subquery ::=](#subquery)

multi_table_insert ::=

*values_clause ::=*, [subquery ::=](#subquery)

values_clause ::=

![](media/SQL/5234b9cafb6bc0a5d51f4c4824c484dd.png)

wait_clause ::=

![](media/SQL/140182321afa39fb9ded6e62d0300e32.png)

#### 전제 조건

SYS 사용자, 테이블 소유자, INSERT ANY TABLE 시스템 권한을 가진 사용자 및
테이블에 대한 INSERT 객체 권한을 가진 사용자만이 이 구문으로 해당 테이블에
레코드를 삽입할 수 있다.

뷰에 레코드를 INSERT할 때, 사용자는 베이스 테이블에 대해서 위와 동일한 권한을
가져야 한다.

#### 설명

명시한 테이블 또는 특정 파티션에 새로운 레코드를 삽입하는 구문이다. 만약 해당
테이블에 인덱스가 존재할 경우엔 인덱스 데이터도 변경될 것이다.

user_name

레코드가 삽입될 테이블의 소유자 이름을 명시한다. 생략하면 Altibase는 그 테이블이
현재 세션에 연결된 사용자의 스키마에 속한 것으로 간주한다.

tbl_name

레코드가 삽입될 테이블의 이름을 명시한다.

view_name

레코드가 삽입될 뷰의 이름을 명시한다.

subquery

레코드를 삽입하려는 뷰를 서브쿼리로 명시한다.

NULL

일부 칼럼의 값은 명시하고 일부 칼럼의 값은 명시하지 않고 데이터를 삽입할 경우,
값을 주지 않은 칼럼에 기본값이 설정되어 있지 않으면 널이 삽입된다. ( TIMESTAMP
칼럼의 기본값은 INSERT 연산이 수행된 시점의 시스템 시각 값이다. 따라서 TIMESTAMP
칼럼의 입력 값을 명시하지 않을 경우 널이 아닌 시스템 시각 값이 삽입된다. )

VALUES 절에 명시적으로 널을 지정하면 널이 삽입된다.

multi_table_insert 절

다중 테이블 삽입절은 서브쿼리에서 생성된 결과 집합의 행을 한 개 이상의 테이블에
삽입하기 위해 사용된다. 서브쿼리의 select 리스트에 수식이 있다면, VALUES 절에서
참조할 수 있도록 수식에 별칭(alias)을 반드시 주어야 한다.

DEFAULT

VALUES 절에 DEFAULT를 명시하면 해당 칼럼에 정의된 기본값이 삽입된다. 전체
칼럼들에 대해 기본값을 삽입하려면 DEFAULT VALUES 절을 사용한다.

TIMESTAMP 칼럼에 DEFAULT를 명시하면 시스템 시각 값이 삽입될 것이다.

INSERT \~ SELECT

SELECT 질의 결과를 테이블에 삽입하는 구문이다. 삽입할 테이블과 조회하는 테이블이
같아도 된다. 삽입할 칼럼의 개수와 조회하는 칼럼의 개수는 동일해야 하며, 대응하는
칼럼은 서로 호환 가능한 데이터 타입이어야 한다.

*returning_clause*

DELETE 구문의 returning_clause를 참고하라.

*wait_clause*

wait_clause에 대한 설명은 SELECT문의 FOR UPDATE 절 참조한다.

#### HINTS 옵션

힌트의 문법과 자세한 설명은 "[힌트 구문](#hint_syntax)"과 "[힌트
목록](#힌트-목록)"을 참고하기 바란다.

#### 주의 사항

INSERT 문으로 데이터를 입력할 때, 다음의 사항들을 유념해야 한다.

-   명시한 칼럼의 개수와 삽입할 값들의 개수는 동일해야 하며 호환 가능한 데이터형
    이어야 한다.

-   파티션을 지정할 경우 해당 파티션에 일치하지 않는 값은 입력할 수 없다.

-   기본값이 정의되어 있지 않고 NOT NULL 제약이 없는 칼럼에 입력값을 명시하지
    않고 INSERT를 수행할 경우, NULL이 삽입된다.

-   CHECK 제약조건으로 인해 INSERT가 실패할 수 있다.

Direct-Path INSERT사용에는 다음과 같은 제약이 있다.

-   대상 테이블은 디스크 테이블이어야 하며, LOB 칼럼 또는 인덱스를 가질 수 없다.

-   이중화 대상 테이블에 대해서 Direct-Path INSERT를 사용할 수 없다.

-   대상 테이블은 트리거나 참조 무결성 제약조건을 가질 수 없다.

-   대상 테이블은 CHECK 제약조건을 가질 수 없다.

#### 예제

##### 단순 데이터 입력

\<질의\> 이름이 Louise Leroux인 고객 정보 입력

INSERT INTO customers VALUES ( '25', 'Leroux', 'Louise', 'student',

'025282222', 'F', '0101', 150763, '\#3 825 - 17th Ave SW Calgary Canada');

1 row inserted.

\<질의\> Rosalia Jung인 고객의 정보 중 사번, 이름, 성별만 입력

INSERT INTO employees(eno, e_firstname, e_lastname, sex) VALUES(21, 'Rosalia',
'Jung', 'F');

1 row inserted.

\<질의\> 여러 개의 레코드를 한번에 입력(Multi Row Insert)

INSERT INTO GOODS VALUES('Y111100001', 'YY-300' , 'AC0001', 1000 , 78000),
('Y111100002', 'YY-310' , 'DD0001', 100 , 98000), ('Y111100003', 'YY-H5000',
'AC0002', 780 , 35800);

3 rows inserted.

##### 복합 데이터 입력

\<질의\> 지연중인 주문에 대한 고객 번호와 주문일을 orders 테이블에서
delayed_processing 테이블로 복사하라.

iSQL\> CREATE TABLE delayed_processing(

cno CHAR(14), order_date DATE);

Create success.

iSQL\> INSERT INTO delayed_processing

SELECT cno, order_date

FROM orders

WHERE PROCESSING = 'D';

1 row inserted.

##### 파티션에 데이터 입력

CREATE TABLE T1 ( I1 INTEGER, I2 INTEGER )

PARTITION BY RANGE ( I1 )

(

PARTITION P1 VALUES LESS THAN ( 300 ),

PARTITION P2 VALUES LESS THAN ( 400 ),

PARTITION P3 VALUES DEFAULT

) TABLESPACE SYS_TBS_DISK_DATA;

INSERT INTO T1 PARTITION ( P1 ) VALUES ( 123, 456 );

1 row inserted.

##### Direct-Path INSERT 힌트 사용한 입력

\<질의\> T1테이블의 모든 데이터를 Direct-Path INSERT 방식으로 T2테이블에
입력한다.

INSERT /\*+ APPEND \*/ INTO T2 SELECT \* FROM T1;

##### 다중 테이블 삽입

\<질의\> 한번에 여러 개의 행을 하나의 테이블에 삽입한다.

CREATE TABLE t (

pid INTEGER,

fname VARCHAR(20),

lname VARCHAR(25));

INSERT INTO t VALUES (1, 'Dan', 'Morgan'), (2, 'Jeremiah', 'Wilton'), (3,
'Helen', 'Lofstrom');

\<질의\> 서브쿼리의 결과를 여러 테이블에 삽입한다.

CREATE TABLE sal_history (

eno INTEGER,

join_date DATE,

salary NUMBER(10,2));

CREATE TABLE dno_history (

eno INTEGER,

dno SMALLINT,

chg_date DATE);

INSERT ALL

INTO sal_history VALUES(emp_id,join_date,salary)

INTO dno_history VALUES(emp_id,dept_id,sysdate)

SELECT eno EMP_ID, join_date, salary, dno DEPT_ID

FROM employees;

##### Returing 절을 사용한 입력

\<질의\> 다음 예제는 입력된 행의 값을 출력 바인드 변수 :v1, :v2로 반환한다.

iSQL\> create table employees ( eno integer, ename varchar(20));

Create success.

iSQL\> var v1 output integer;

iSQL\> var v2 output varchar(30);

iSQL\> prepare insert into employees values (1, 'jake') return eno, ename into
:v1, :v2;

1 row inserted.

iSQL\> print var

[ HOST VARIABLE ]

\-------------------------------------------------------

NAME TYPE VALUE

\-------------------------------------------------------

V1 INTEGER 1

V2 VARCHAR(30) jake

##### 조인 뷰에 데이터 입력

\<질의\> employees와 departments 테이블의 조인 뷰를 생성한 후, 레코드를
삽입한다.

iSQL\> CREATE VIEW simple_emp AS

SELECT eno, e_lastname, e_firstname, emp.dno dno

FROM employees emp, departments dept

WHERE emp.dno = dept.dno;

Create success.

iSQL\> select \* from simple_emp;

ENO E_LASTNAME E_FIRSTNAME DNO

\-------------------------------------------------------------------------

3 Kobain Ken 1001

16 Chen Wei-Wei 1001

.

.

.

20 Blake William 4002

19 rows selected.

iSQL\> INSERT INTO simple_emp(eno, e_lastname, e_firstname, dno) VALUES(50,
'Kim', 'Yong', 1001);

1 row inserted.

iSQL\> select \* from simple_emp;

ENO E_LASTNAME E_FIRSTNAME DNO

\-------------------------------------------------------------------------

3 Kobain Ken 1001

16 Chen Wei-Wei 1001

50 Kim Yong 1001

.

.

.

20 Blake William 4002

20 rows selected.

### LOCK TABLE

#### 구문

lock_table ::=

![](media/SQL/e99f48f993166dcd8201c1ef39f47f4d.png)

#### 전제 조건

SYS 사용자, 테이블의 소유자와 LOCK ANY TABLE 시스템 권한을 가진 사용자만이 이
구문으로 테이블을 잠글수있다.

#### 설명

lock_mode에 명시한 잠금 모드로 특정한 모드 내에서 테이블 잠금(lock table)을
설정하는 기능이다. 테이블에 잠금이 걸리면 관련 트랜잭션이 커밋되거나 롤백될
때까지 계속 그 잠금이 유지된다.

user_name

잠금이 걸릴 테이블의 소유자 이름을 명시한다. 생략하면 Altibase는 그 테이블이
현재 세션에 연결된 사용자의 스키마에 속한 것으로 간주한다.

tbl_name

잠금이 걸릴 테이블의 이름을 명시한다.

lock_mode

테이블 잠금을 설정할 때, 다음의 잠금 모드 중에서 하나를 명시해야 한다.

-   ROW SHARE  
    이 모드로 잠금이 설정된 테이블에 다른 트랜잭션에 의한 동시 접근을 허용한다.
    그러나 다른 사용자들이 독점적인 접근을 위해 이 테이블에 EXCLUSIVE 모드로
    잠금을 거는 것은 금한다.

-   SHARE UPDATE  
    ROW SHARE와 동일한 기능의 잠금 모드이다.

-   ROW EXCLUSIVE  
    이 모드로 잠금이 설정된 테이블에 다른 트랜잭션에 의한 동시 접근을 허용한다.
    그러나 다른 사용자들이 독점적인 접근을 위해 이 테이블에 EXCLUSIVE 또는 SHARE
    모드로 잠금을 거는 것은 금한다. 데이터를 갱신, 삽입하거나 또는 삭제할 때
    자동으로 이 잠금이 획득된다.

-   SHARE ROW EXCLUSIVE  
    다른 트랜잭션이 이 모드로 잠금이 설정된 테이블을 읽는 것이 허용된다. 그러나
    다른 사용자들이 독점적인 접근을 위해 이 테이블에 SHARE 모드로 잠금을 거는
    것은 금한다.

-   SHARE  
    다른 트랜잭션이 이 모드로 잠금이 걸린 테이블을 읽는 것은 허용하지만 갱신하는
    것은 금한다.

-   EXCLUSIVE  
    현재 트랜잭션이 이 모드로 잠금이 걸린 테이블을 읽거나 갱신하는 것은
    허용하지만, 다른 트랜잭션은 불가하다.

WAIT \| NOWAIT

잠금이 획득될 때까지 대기할 지 여부를 지정하는 옵션이다. 생략하면, 행 단위
잠금이 획득될 때까지 무한정 기다린다.

-   WAIT n  
    트랜잭션이 행 단위 잠금(row lock)이 걸리기까지 n 초 만큼 기다리고도 획득에
    실패하면 에러가 반환될 것이다.

-   NOWAIT  
    트랜잭션이 잠금 획득이 즉시 안 될 경우 행 단위 잠금이 걸리기까지 기다리지
    않는다. 이 경우 이미 다른 사용자에 의해서 해당 테이블에 이미 잠금이 걸려
    있다는 것을 나타내는 에러를 반환한다.

UNTIL NEXT DDL

세션이 NON-AUTOCOMMIT 모드일 때 테이블에 DDL(데이터 정의어)을 수행하면, DDL이
실행되기 직전에 자동으로 커밋을 수행한다.

그러나 lock_mode에서 EXCLUSIVE 모드를 지정하고 이 절을 실행하면, DDL을 수행하기
직전에 자동으로 커밋을 수행하지 않는다. 이 기능은 하나의 트랜잭션에 한 번만
수행할 수 있다.

| SQL Statement                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Mode of Table Lock | Lock Modes Permitted? |         |        |          |      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-----------------------|---------|--------|----------|------|
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                    | IS                    | IX      | S      | SIX      | X    |
| SELECT … FROM *tbl_name* …                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | IS                 | Y(IS)                 | Y(IX)   | Y(S)   | Y(SIX)   | N(X) |
| INSERT INTO *tbl_name* …                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | IX                 | Y(IX)                 | Y(IX)   | N(SIX) | N(SIX)   | N(X) |
| UPDATE tbl_name …                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | IX                 | Y\*(IX)               | Y\*(IX) | N(SIX) | N(SIX)   | N(X) |
| DELETE FROM *tbl_name* …                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | IX                 | Y\*(IX)               | Y\*(IX) | N(SIX) | N(SIX)   | N(X) |
| SELECT … FROM *tbl_name* FOR UPDATE …                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | IS                 | Y\*(IX)               | Y\*(IX) | Y\*(S) | Y\*(SIX) | N(X) |
| LOCK TABLE *tbl_name* IN ROW SHARE MODE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | IS                 | Y(IS)                 | Y(IX)   | Y(S)   | Y(SIX)   | N(X) |
| LOCK TABLE *tbl_name* IN ROW EXCLUSIVE MODE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | IX                 | Y(IX)                 | Y(IX)   | N(SIX) | N(SIX)   | N(X) |
| LOCK TABLE *tbl_name* IN SHARE MODE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | S                  | Y(S)                  | N(SIX)  | Y(S)   | N(SIX)   | N(X) |
| LOCK TABLE *tbl_name* IN SHARE ROW EXCLUSIVE MODE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | SIX                | Y(SIX)                | N(SIX)  | N(SIX) | N(SIX)   | N(X) |
| LOCK TABLE *tbl_name* IN EXCLUSIVE MODE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | X                  | N(X)                  | N(X)    | N(X)   | N(X)     | N(X) |
| IS: row share (Intent share lock) IX: row exclusive (Intent exclusive lock) S: share SIX: share row exclusive (Share with Intent exclusive lock) X: exclusive \* Y: 다른 트랜잭션에 의해 행 잠금 충돌이 일어나지 않은 경우, 그 트랜잭션은 잠금 획득이 가능하다. 그렇지 않으면 기다림이 발생한다. 괄호 내에 표시된 잠금 타입은: 1. 다른 트랜잭션에 의해 현재의 잠금 모드 전환이 허용되는 경우(Y), 현재 걸려있는 잠금 타입이 괄호 안의 타입으로 전환된다. 2. 다른 트랜잭션에 의해 현재의 잠금 모드 전환이 허용되지 않는 경우(N), 잠금 타입은 현재 잠금을 획득하고 있는 트랜잭션이 새로운 잠금을 획득할 때만 괄호 안의 타입으로 전환이 가능하다. |                    |                       |         |        |          |      |

[표 4‑1] Summary of Table Locks

#### 예제

다음은 LOCK TABLE과 SELECT 문이 사용 될 때 Altibase가 데이터 동시성, 무결성,
그리고 일관성을 어떻해 관리하는가를 보여주는 예제이다.

| Transaction A                                                                                                                                                                 | Time Point | Transaction B                                                                                                                       |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------|
| iSQL\> AUTOCOMMIT OFF; Set autocommit off success.                                                                                                                            |            | iSQL\> AUTOCOMMIT OFF; Set autocommit off success.                                                                                  |
|                                                                                                                                                                               | 1          | (request X lock on employees) iSQL\> LOCK TABLE employees IN EXCLUSIVE MODE; Command execute success. (acquire X lock on employees) |
| iSQL\> DROP TABLE employees; [ERR-11170: The transaction has exceeded the lock timeout specified by the user.]                                                                | 2          |                                                                                                                                     |
|                                                                                                                                                                               | 3          | iSQL\> UPDATE employees SET salary = 2500000 WHERE eno = 15; 1 row updated.                                                         |
| (request S lock on employees) iSQL\> LOCK TABLE employees IN SHARE MODE; (the request conflicts with the X lock already held by transaction B) wait wait wait                 | 4          |                                                                                                                                     |
|                                                                                                                                                                               | 5          | iSQL\> COMMIT; Commit success. (release X lock on employees)                                                                        |
| (resume) Lock success. (acquire S lock on employees) iSQL\> SELECT salary FROM employees WHERE eno = 15; SALARY -------------- 2500 1 row selected. (커밋된 데이터가 보인다.) | 6          |                                                                                                                                     |
| iSQL\> ROLLBACK; Rollback success. (release S lock on employees)                                                                                                              | 7          |                                                                                                                                     |
| iSQL\> LOCK TABLE employees IN EXCLUSIVE MODE; Lock success. (acquire X lock on employees)                                                                                    | 8          |                                                                                                                                     |
|                                                                                                                                                                               |            | iSQL\> SELECT SALARY FROM employees WHERE eno = 15; wait wait wait                                                                  |
| iSQL\> UPDATE employees SET eno = 30 WHERE eno = 15; 1 row updated.                                                                                                           | 10         |                                                                                                                                     |
| iSQL\> COMMIT; Commit success. (release X loc on employees)                                                                                                                   | 11         |                                                                                                                                     |
|                                                                                                                                                                               | 12         | (resume) SALARY -------------- 2500 1 row selected.                                                                                 |

### SELECT 

#### 구문

select ::=

[with_clause ::=](#with_clause), [subquery ::=](#subquery), [for_update_clause
::=](#for_update_clause)

with_clause ::=

subquery ::=

[select_clause ::=](#select_clause), [order_by_clause ::=](#order_by_clause),
[limit_clause ::=](#limit_clause)

select_clause ::=

![](media/SQL/77d1a3feb68a0257346ff3590901be12.png)

[hints ::=](#hints_diagram), [select_list ::=](#select_list), [tbl_reference
::=](#tbl_reference), [where_clause ::=](#where_clause),
[hierarchical_query_clause ::=](#hierarchical_query_clause), [group_by_clause
::=](#group_by_clause)

select_list ::=

tbl_reference ::=

![](media/SQL/e71b7bc2eebb6dec22a57132da33f80c.png)

[single_table ::=](#single_table), [joined_table ::=](#joined_table)

single_table ::=

pivot_clause ::=

pivot_for_clause ::=

pivot_in_clause ::=

unpivot_clause ::=

[pivot_for_clause ::=](#pivot_for_clause)

unpivot_in_clause ::=

joined_table ::=

[tbl_reference ::=](#tbl_reference), [single_table ::=](#single_table),
[apply_type ::=](#apply_type)

join_type ::=

apply_type ::=

where_clause ::=

hierarchical_query_clause ::=

group_by_clause ::=

rollup_cube_clause ::=

grouping_sets_clause ::=

grouping_expression_list ::=

expression_list ::=

order_by_clause ::=

limit_clause ::=

for_update_clause ::=

![](media/SQL/f241bd3f3359d8cb294e30715f7b2724.png)

#### 전제 조건

SYS 사용자, 테이블 소유자, SELECT ANY TABLE 시스템 권한을 가진 사용자 및
테이블에 대한 SELECT 객체 권한을 가진 사용자만이 이 구문으로 해당 테이블에서
데이터를 조회할 수 있다.

#### 설명

한 개 이상의 테이블 또는 뷰에서 데이터를 검색하는 구문이다.

with_clause

Altibase는 with_clause 절을 인라인 뷰 또는 임시 테이블로 처리하여 최적화한다.

일반적인 WITH query_name절은 AS 다음에 따라오는 부질의(subquery)에 이름을
부여한다. 부질의에 부여된 이름은 주질의 내의 여러 위치에서 참조될 수 있다.

그러나 재귀적인 WITH 구문(이하 recursive with 또는 재귀 질의)에서는 반드시
query_name 뒤에 칼럼의 별명을 지정하고, 부질의 내에서 집합 연산자를 사용해야
해당 질의를 반복적으로 수행할 수 있다. subquery 내에는 집합 연산자를 기준으로 두
개의 질의가 존재하며, 앞의 질의는 주 질의(기준 질의)가 되고 뒤의 질의가 재귀
질의가 된다. 재귀 질의는 프로퍼티 RECURSION_LEVEL_MAXIMUM에 설정한 레벨
값(기본값 1000)까지 최대 출력된다. 자세한 내용은 Altibase 매뉴얼 중 *General
Reference*의 Altibase 프로퍼티 장을 참조한다.

사용자는 이 절을 주질의 및 대부분 유형의 부질의에 명시할 수 있다.

제약 사항:

-   하나의 SQL 문에 하나의 with_clause만 명시할 수 있다. query_name은 자신을
    정의하는 부질의에서는 사용할 수 없다. 단 with_clause 안에서 여러 개의 쿼리
    이름을 정의하는 경우, 뒤이어 정의되는 다른 부질의에는 앞서 정의한 다른 쿼리
    이름을 사용할 수 있다.

-   RECURSIVE WITH 구문에서 주 질의와 재귀 질의의 위치가 변경되면 안된다. 또한
    query_name을 재귀 질의에서 한 번은 명시적으로 참조해야 한다. 그러나 재귀
    질의에서는 집계 함수, DISTINCT 키워드, GROUP BY 절을 사용할 수 없다.

-   RECURSIVE WITH 구문의 주 질의에 query_name을 참조하는 서브쿼리를 사용할 수
    없다.

-   RECURSIVE WITH 구문의 재귀 질의에 query_name을 참조하는 뷰 또는 Outer Join의
    오른쪽 테이블에 사용할 수 없다.

TOP (*expr*)

쿼리의 결과 집합 중 반환할 행의 개수를 지정하는 절이다. *expr*에는 정수만 올 수
있다.

select_list 절

DISTINCT를 명시할 경우 결과 집합에서 중복된 레코드는 제거된다.

만약 GROUP BY 절이 존재한다면 상수, 집계 함수(aggregate functions), GROUP BY
절에 명시된 표현식과 이들을 조합한 표현식만 SELECT 리스트에 명시 가능하다.

SELECT 리스트가 칼럼이 포함되지 않은 수식 또는 상수로만 이루어져 있는 경우, FROM
절 이하를 생략할 수 있다.

SELECT 리스트에 \*만 명시한 것은 FROM 절의 모든 테이블과 뷰의 모든 칼럼들을
의미한다. SELECT 리스트에 \*가 칼럼 또는 수식과 함께 명시된 경우에도 마찬가지
의미이다.

FROM 절

같은 별명(alias_name)을 FROM 절에 두 번 이상 사용할 수 없다. 같은 테이블 명을
FROM절에 여러 번 사용할 때, 다른 별명을 주어야 한다. 즉, 별명을 명시하지 않고
같은 테이블 명을 두 번 이상 사용할 수 없다.

FROM절에 올 수 있는 테이블 또는 뷰의 최대 개수는 32개이다.

###### **OUTER JOIN**

조인 조건을 만족하지 않는 데이터를 처리하기 위한 JOIN의 확장 형태이다. (INNER)
JOIN이 두 테이블에서 키 값이 일치하는 데이터만 가져오는 것에 비해 OUTER JOIN은
어느 한 쪽의 데이터를 모두 가져온다. 즉, 한 테이블의 행에 대응하는 행이 다른
테이블에 존재하지 않을 때, 빈 칼럼들에 대해서 결과 집합에는 NULL로 채워져서
반환된다.

###### **인라인 뷰(Inline View)**

FROM 절에 오는 부질의(subquery)를 인라인 뷰라고 한다.

###### **Lateral View**

FROM 절에 오는 인라인 뷰는 FROM 절에 나열된 다른 객체나 상위 쿼리에 있는 객체를
참조할 수 없다. 그러나 FROM 절의 인라인 뷰를 Lateral View로 정의하면 인라인 뷰의
외부 객체를 참조할 수 있게 된다.

인라인 뷰를 Lateral View로 정의하려면, LATERAL 또는 APPLY 키워드를 인라인 뷰
앞에 지정하면 된다. 단, Lateral View가 참조할 수 있는 객체는 해당 Lateral View의
왼쪽에 지정된 객체들뿐이다. Lateral View로 정의하더라도 Lateral View가 외부
객체를 참조하지 않으면, Altibase 서버가 해당 Lateral View를 일반적인 인라인 뷰로
취급한다.APPLY 키워드는 인라인 뷰를 Lateral View로 정의하면서 APPLY 키워드의
왼쪽 객체와 해당 Lateral View의 조인도 함께 수행한다. 일반적인 조인문이 ON
키워드 뒤에 조인 조건을 지정하는 것과 달리, APPLY 키워드를 사용하는 조인의
경우에는 조인 조건이 필요 없다.

APPLY 키워드를 사용해서 다음의 조인 유형을 지정할 수 있다.

-   CROSS APPLY는 왼쪽 객체와 Lateral View를 Inner Join 할 것을 지정한다.

-   OUTER APPLY는 왼쪽 객체와 Lateral View를 Left Outer Join 할 것을 지정한다.

주의사항:

아래와 같이 Lateral View를 사용하는 경우, 오류 메시지가 반환된다.

-   Lateral View에서 Fixed Table을 참조하는 경우

-   Lateral View에 PIVOT 절, UNPIVOT 절이 사용된 경우

-   Lateral View에서 해당 Lateral View의 오른쪽에 지정된 객체를 참조하는 경우

-   Lateral View가 참조하는 객체와 Lateral View를 Right Outer Join 또는
    Full-Outer Join을 하는 경우

-   LATERAL 키워드와 APPLY 키워드를 붙여서 같이 사용한 경우

-   APPLY 키워드와 ON 절을 함께 사용한 경우

###### **pivot_clause**

pivot_clause는 데이터 집계 연산 및 별개의 행으로 존재하는 데이터를 칼럼으로
재배열하여 보여주기 위해 사용할 수 있다. 이것은 GROUP BY 절에 두 개의 칼럼을
사용할 때보다 데이터를 더 읽기 쉽게 보여준다.  
편의상, 많은 수의 칼럼 출력 또는 변형 연산의 결과로 생기는 특정 칼럼들의 이름을
명시하는 어려움을 방지하기 위해서 pivot_clause는 일반적으로 인라인 뷰와 함께
사용된다.  
pivot_clause는 다음의 단계를 수행한다.

1.  먼저 pivot_clause 는 마치 GROUP BY 절처럼 그룹 연산을 수행한다. 그 결과는
    pivot_clause내의 참조되지 않은 모든 칼럼과 pivot_in_clause에 명시된 값에
    대해 그룹화된다.

2.  다음으로 pivot_clause는 결과로 나온 그룹화된 칼럼들과 집계된 값들을 회전된
    표 형식으로 배열한다.

###### **pivot_for_clause**

pivot_in_clause에 명시된 값이 칼럼 형태로 바꾸어질 때 이에 해당하는 칼럼 이름을
명시한다.

###### **pivot_in_clause**

pivot_for_clause에 명시된 칼럼들에 존재하는 값을 이 절에 명시할 수 있다. 이
값들은 pivot 연산에서 칼럼 이름으로 사용될 것이다.

###### **unpivot_clause**

unpivot_clause는 칼럼의 데이터들을 행으로 변환시켜 결과를 반환한다.

INCLUDE \| EXCLUDE NULLS 옵션은 UNPIVOT 절로 생성되는 칼럼의 값에 NULL을 허용할
것인지를 선택할 수 있다. EXCLUDE NULLS는 NULL 값이 생략된 결과를 반환하며,
생략하면 EXCLUDE NULLS로 동작한다.

column_name에는 UNPIVOT 구문으로 생성되는 칼럼에 해당하는 값들이 반환되는 칼럼
이름을 지정한다.

unpivot_clause에서 사용한 칼럼의 개수만큼 pivot_for_clause 와 pivot_in_clause에
사용되는 칼럼 개수도 같아야 한다. 또한 alias의 개수도 같아야 한다.

unpivot ( ( column, column ) for ( column, column ) in ( ( column, column ) as (
column, column ) ) );

다음처럼 칼럼 개수가 다른 구문은 지원하지 않는다.

unpivot ( ( column, column ) for column in ( ( column, column ) as column ) );

###### **Table Function**

사용자 정의 함수에서 Associative Array 타입이나 Record 타입을 사용할 때 반환되는
결과를 테이블 형태로 변환하여 출력한다.

where 조건절

WHERE 절의 조건에 대한 설명은 8장 조건 연산자를 참고한다.

Hierarchical Query 절

계층적 질의(Hierarchical query)란 데이터 조회시 계층적 구조로 출력되는
쿼리문이다. 테이블에 부모, 자식 관계를 가지는 데이터가 존재하는 경우 이 쿼리문을
이용해서 부모, 자식 관계를 계층적으로 출력할 수 있다. 즉, 주어진 검색 조건을
갖는 루트 행에 대하여, 그 행과 그의 종속 행에 대한 계층적 조건을 만족하는 행들을
검색한다.

만약 ORDER BY 절 또는 GROUP BY 절을 사용하여 계층적 데이터를 조회하면, CONNECT
BY절로 수립된 계층적 순서가 바뀔 수 있으므로 주의가 필요하다. 단, ORDER SIBLINGS
BY를 사용하면 계층 구조를 보존하면서 동일한 레벨의 자식들 사이에서 순서를 정할
수 있다.

###### **START WITH 절**

계층적 질의의 루트 행으로 사용될 행을 식별하는 조건을 명시하는 절이다. 이 조건을
만족하는 모든 행들이 루트 행으로 사용된다. 이 절을 생략하면 Altibase는 테이블에
있는 모든 행들을 루트 행으로 사용한다.

ROWNUM 의사칼럼은 이 절에 사용될 수 없다.

###### **CONNECT BY 절**

계층 구조에서 부모 행들과 자식 행들간의 관계를 식별하는 조건을 명시한다.

CONNECT BY 절은 부질의를 포함할 수 없고 조인과 함께 사용될 수도 없다.

CONNECT BY 절은 WHERE 절 이후 ORDER BY, GROUP BY, HAVING 절 이전에 사용하여야
한다.

NOCYLE 키워드는 계층적 질의의 결과 집합에 순환구조가 존재하더라도, 순환이
발생하기 전까지의 행을 반환할 것을 데이터베이스에 요구한다.

###### **SYS_CONNECT_BY_PATH함수는 계층적 질의에서 현재 행까지의 PATH 정보를 쉽게 가져올 수 있다. 이 함수에 대한 자세한 내용은 "6장 SQL 함수"를 참고하라.**

###### **PRIOR 연산자**

이전에 검색된 행과 현재 행을 구분하기 위해서 PRIOR 연산자를 사용한다. 즉,
부모행을 언급하기 위해 반드시 PRIOR 연산자를 사용해야 한다.

PRIOR 연산자는 CONNECT BY 절을 포함하는 질의문의 SELECT 리스트, WHERE 절, 또는
CONNECT BY 절에서만 사용할 수 있다.

질의에 집합 연산자 (UNION, INTERSECT, 등)가 사용되면, PRIOR 연산자는 ORDER BY
절에 올 수 없다.

###### **CONNECT_BY_ROOT 연산자**

CONNECT_BY_ROOT는 계층적 질의에서만 사용 가능한 단일 연산자이다. 칼럼에 이
연산자를 사용하면 루트 행의 칼럼 값을 반환한다.

START WITH 조건 또는 CONNECT BY 조건에 이 연산자를 사용할 수 없다.

###### **CONNECT_BY_ISLEAF 의사칼럼**

CONNECT_BY_ISLEAF 의사칼럼은 현재 행이 CONNECT BY 조건에 의해 정의된 트리에서
리프 노드(자식 노드가 없는 노드)인 경우 1을 반환하고, 그렇지 않으면 0을
반환한다.

###### **LEVEL 의사칼럼**

계층적 질의를 포함하는 SQL문은 *select_list*에 LEVEL 의사칼럼을 포함할 수 있다.
LEVEL 의사칼럼은 루트 행과 종속 행간의 계층적 거리를 나타낸다. 즉, 루트 행의
LEVEL은 1이고, 자식 행의 LEVEL은 2, 손자 행의 LEVEL은 3, 등이 된다.

LEVEL의사칼럼은 WHERE 절, ORDER BY 절, GROUP BY 절, HAVING 절에서도 사용
가능하다. 또한, LEVEL 의사칼럼은 다음 예처럼 쿼리문에 CONNECT BY 절이 없더라도
*select_list* 에 올 수 있다:

select level from t1;

###### **IGNORE** 

행들간 계층 관계가 순환 형태를 이룰 경우 Altibase는 오류를 반환한다. (여기서
순환이란 한 행이 다른 행의 부모 행도 되고 자식 행도 되는 경우를 말한다.) 단,
IGNORE LOOP이 명시되었을 경우, 질의 수행시의 순환 형성이 오류를 발생시키지 않고,
순환 형태의 행들이 질의 결과 집합에서 제거된다.

GROUP BY 절

GROUP BY 절은 주어진 하나 이상의 표현식에 대해서 같은 값을 가지는 레코드들끼리
그룹짓고, 각 그룹별로 집계한 정보를 한 행으로 반환받기 위해 사용되는 절이다.

WHERE 조건을 사용하여 반환되는 그룹을 제한할 수 없는 대신에, HAVING 절을
사용하여 반환되는 그룹을 제한할 수 있다.

HAVING 및 GROUP BY 절은 WHERE 절과 *hierarchical_clause* 뒤에 위치시킨다. 만약
ORDER BY 절이 있다면 이는 쿼리문의 맨 마지막에 와야 한다.

rollup_cube_clause, grouping_sets_clause

ROLLUP, CUBE, GROUPING SETS는 GROUP BY절이 확장된 것으로써, 여러 개의 그룹화
세트를 지정할 수 있다. 즉, ROLLUP, CUBE 또는 GROUPING SETS를 사용하면 GROUP BY
절을 포함하는 여러 쿼리를 UNION ALL로 결합한 것과 동일한 결과를 얻을 수 있다.

제약 사항:

-   GROUP BY 절에서 ROLLUP ,CUBE 또는 GROUPING SETS는 한 번만 명시할 수 있다.

-   SELECT 대상에 부질의(subquery)를 인자로 가지는 집계 함수를 사용할 수 없다.

-   ROLLUP, CUBE 또는 GROUPING SETS과 window 함수를 함께 사용할 수 없다.

-   CUBE절에 최대 15개의 수식을 지정할 수 있다.

-   GROUPING SETS와 중첩 집계 함수를 함께 사용할 수 없다.

ROLLUP

ROLLUP은 GROUP BY 절과 함께 사용되며, GROUP BY 절에 의해서 그룹 지어진 집합
결과에 대하여 상세한 정보를 반환하는 기능을 수행한다.

SUM연산과 함께 사용되면, 총계뿐만 아니라 ROLLUP에서 지정하는 칼럼들의 그룹별
소계까지 구한다.

ROLLUP은 그룹화 칼럼들의 개수가 n개일 때 (n+1)개의 GROUP BY가 수행된다. 예를
들어, GROUP BY 절 내에 ROLLUP(a,b,c)를 사용하면 반환되는 그룹의 조합은 다음과
같다:

>   (a,b,c), (a,b), (a), ( )

###### **부분 롤업(Partial ROLLUP)**

아래 예제와 같이 GROUP BY의 그룹화 칼럼 중 일부분에만 ROLLUP을 적용하는 것을
"부분 ROLLUP"이라고 한다:

GROUP BY a, ROLLUP(b, c), d

이 경우, 반환되는 그룹의 조합은 다음과 같다:

(a, d, b, c), (a, d, b), (a, d)

###### **복합 칼럼(Composite Columns) 사용하기**

아래 예제와 같이 ROLLUP 절에 복합 칼럼의 리스트를 명시할 수 있다:

GROUP BY ROLLUP((a, b), (c, d))

이 경우, 반환되는 그룹의 조합은 다음과 같다:

(a, b, c, d), (a, b), ( )

CUBE

CUBE는 명시된 그룹화 칼럼들의 가능한 모든 조합으로 그룹화를 수행한다. 그룹화
칼럼의 개수가 n개일 때, CUBE는 2n개의 조합에 대해 그룹화를 수행한다. 예를 들어,
GROUP BY CUBE(a,b,c)를 명시하면, (23=8)개의 조합이 아래와 같이 반환된다:

>   (a,b,c), (a,b), (a,c), (b,c), (a), (b), (c), ( )

###### **부분 큐브(Partial CUBE)**

부분 CUBE는 부분 ROLLUP과 유사하다. 즉, CUBE 연산자에 명시한 칼럼들의 가능한
모든 조합이 CUBE 바깥에 있는 칼럼과 함께 결합되어 반환되는 그룹이 결정된다. 부분
CUBE의 문법은 다음과 같다:

GROUP BY a, CUBE(b, c), d

이 경우, 아래의 조합에 대한 소계가 반환된다:

(a, d, b, c), (a, d, b), (a, d, c), (a, d)

###### **복합 칼럼(Composite Columns) 사용하기**

아래 예제와 같이 CUBE 절에 복합 칼럼의 리스트를 명시할 수 있다:

GROUP BY CUBE((a, b), (c, d))

이 경우, 반환되는 그룹의 조합은 다음과 같다:

(a, b, c, d), (a, b), (c, d), ( )

GROUPING SETS

ROLLUP이나 CUBE에 의해 생성되는 그룹화 세트 중에서 일부만 필요한 경우에 GROUPING
SETS에 원하는 그룹화 세트만 지정할 수 있다.

SUM연산과 함께 사용되면, GROUPING SETS에서 지정하는 그룹별 총계를 구한다.

GROUPING SETS은 그룹화된 칼럼의 개수가 n개일 때 n개의 GROUP BY가 수행된다. 예를
들어, GROUP BY절 내에 GROUPING SETS(a, b, c)를 사용하면 반환되는 그룹의 조합은
다음과 같다.

>   (a), (b), (c)

###### **부분 GROUPING SETS (Partial GROUPING SETS)**

아래 예제와 같이 GROUP BY의 그룹화 칼럼 중 일부분에만 GROUPING SETS을 적용하는
것을 "부분 GROUPING SETS"이라고 한다.

GROUP BY a, GROUPING SETS(b, c), d

이 경우, 반환되는 그룹의 조합은 다음과 같다:

(a, b, d), (a, c, d)

###### **복합 칼럼(Composite Columns) 사용하기**

아래 예제와 같이 GROUPING SETS절에 복합 칼럼의 리스트를 명시할 수 있다.

GROUP BY GROUPING SETS((a, b), (c, d))

이와 같이 GROUPING SETS 목록에서 내부 괄호 안에 2개 이상의 칼럼들이 있는 경우
하나의 칼럼으로 취급된다. 반환되는 그룹의 조합은 다음과 같다.

(a, b), (c, d)

###### **빈 그룹(Empty Group) 사용하기**

아래 예제와 같이 GROUPING SETS절에 빈 괄호("()")를 사용해서 '빈 그룹'을 명시할
수 있다.

GROUP BY GROUPING SETS((), a, b, c)

빈 그룹은 그룹화 없이 총계를 구하기 위해 사용할 수 있다.

HAVING 조건절

HAVING 절에는 상수, 집계 함수(aggregate functions), GROUP BY 절에 명시된
표현식과 이들을 조합한 표현식만 올 수 있다.

이 절은 명시된 조건이 참인 그룹에 해당하는 레코드만 반환한다.

HAVING 절의 조건문에 대한 자세한 설명은 "8장 조건 연산자"를 참고하기 바란다.

UNION (ALL), INTERSECT, MINUS

집합 연산자는 두 SELECT 문의 결과 집합을 하나로 결합한다. 각 질의가 반환하는
칼럼들의 개수와 데이터 타입이 동일해야 하지만, 칼럼 길이는 달라도 된다. 집합
연산자의 앞 부분에 위치하는 *select_list* 의 표현식 이름이 전체 결과 집합의 칼럼
이름이 될 것이다.

집합 연산자에 대한 자세한 설명은 5장 집한 연산자를 참고한다.

ORDER BY 절

검색된 레코드들을 정렬하는 절이다. 결과 집합은 오름차순 또는 내림차순으로 정렬
가능하다. 기본으로 오름차순 정렬된다.

ORDER BY 절 없이 같은 질의를 반복해서 수행할 때, 결과 집합이 일관되게 정렬된다는
보장이 없다.

ORDER BY 절은 SELECT 문에서 한번만 올 수 있다. 이는 부질의 (subquery)에서는
사용할 수 없다.

ORDER BY 절에 표현식을 명시한 경우에는 표현식 연산의 결과 값에 대해 정렬된다.
표현식은 *select_list* 또는 FROM 절의 테이블 또는 뷰의 컬럼을 기반으로 작성될
것이다. ORDER BY 절에 상수를 명시한 경우에는 *select_list* 내에서의 그 위치에
해당하는 검색 대상 값에 대해 정렬 한다.

집합 연산자(UNION, INTERSECT 등)를 사용한 경우, 위치(position) 또는 검색 대상의
별명만 ORDER BY 절에 사용 가능하다.

GROUP BY가 존재할 경우 그룹 표현식만 사용 가능하다.

ORDER BY 절에 다수의 표현식도 올 수 있다. 결과 집합은 먼저 첫 번째 표현식의 값을
기준으로 정렬되고, 첫번째 표현식의 값이 같은 레코드들은 두번째 표현식의 값을
기준으로 정렬되며, 같은 방식으로 이 후 표현식에 대해서도 정렬된다.

오름차순의 인덱스가 정렬 기준 칼럼에 존재한다면, 오름차순으로 정렬할 때는 다른
모든 것들의 뒤에, 그리고 내림차순으로 정렬할 때는 다른 다른 것들의 앞에, NULL 이
정렬된다. 내림차순의 인덱스가 정렬 기준 칼럼에 존재한다면, 오름차순으로 정렬할
때는 다른 모든 것들의 앞에, 그리고 내림차순으로 정렬할 때는 다른 다른 것들의
뒤에, NULL 이 정렬된다. 인덱스가 정렬 기준 칼럼에 존재하지 않는다면, 정렬 순서에
상관없이 NULL은 다른 모든 것들의 뒤에 나타난다.

검색 대상에 DISTINCT를 사용하면, ORDER BY 절에는 SELECT 리스트내의 표현식 또는
이들 표현식의 조합만 올 수 있다.

GROUP BY 절이 있다면, 다음의 표현식이 ORDER BY 절에 올 수 있다.

-   상수

-   집계 함수 (aggregate functions)

-   GROUP BY 절의 표현식

-   위의 조합으로 이루어진 표현식

NULLS FIRST 또는 NULLS LAST 키워드를 사용해서 NULL을 정렬 순서에서 맨 처음 또는
맨 마지막에 위치시킬 수 있다.

LIMIT 절

LIMIT 절은 반환되는 행의 개수를 제한하기 위해 사용된다.

-   row_offset: 반환할 첫번째 레코드를 지정한다. 생략하면 전체 결과 집합의
    첫번째 레코드부터 반환될 것이다.

-   row_count: 반환할 레코드의 개수를 지정한다.

부질의에서도 LIMIT절을 사용할 수 있다.

FOR UPDATE 절

현재 트랜잭션이 끝날 때까지 다른 사용자들이 행(row)을 잠그거나 수정할 수 없도록
선택된 행을 잠근다.

WAIT 옵션은 테이블의 잠금을 획득하기 위해 얼마나 대기할지를 지정한다. 적용할 수
있는 시간 단위는 second(초), millisecond(msec, 1/1000초), microsecond(usec,
1/1000000초)이며 표기하지 않으면 초 단위가 적용된다. 반면, NOWAIT 옵션은 잠금을
획득할 테이블이 이미 다른 트랜잭션에 의해 잠금이 걸린 상태라면 기다리지 말 것을
지시한다.

FOR UPDATE 절은 최 상위 SELECT 문에서만 사용 가능하다. 즉, 부질의에는 사용할 수
없다. 그러므로 다음과 같은 질의는 사용할 수 없다:  
select eno from employees where (select eno from departments for update);

FOR UPDATE 절은 DISTINCT, GROUP BY절, 집계 함수, 집합 연산자(UNION, INTERSECT
등)와 함께 사용 할 수 없다.

#### 조인

조인이란 두 개 이상의 테이블, 뷰, materialized 뷰로부터 로우를 결합하는 것을
일컫는다. 쿼리의 FROM 절에 여러 테이블이 있을 때 조인이 수행된다.

조인 조건(join condition)은 두 테이블을 결합하는 방법을 정의한다. 조인 조건은
FROM 절이나 WHERE 절 중의 하나에 지정할 수 있다. 조인 조건에 있는 칼럼이 select
리스트에 반드시 있을 필요는 없다. 조인 조건은 주로 각 테이블로부터 두 칼럼을
비교하는데, Altibase는 조인 조건이 TRUE로 판정되는 각 테이블의 로우를 결합해서
반환한다.

세 개 이상의 테이블을 조인하는 경우, Altibase는 두 테이블을 먼저 조인한 다음 그
결과를 다른 테이블과 조인한다. 쿼리 옵티마이저는 조인할 테이블의 순서를 결정할
때 조인 조건, 인덱스, 통계 정보 등에 기반한다.

\* 주의: LOB 칼럼은 조인 조건에 사용될 수 없다.

Altibase는 아래의 조인을 지원한다.

-   Cross Join

-   Inner Join

-   Outer Join

-   Semi Join

-   Anti Join

##### Cross Join

조인 조건을 갖지 않는 두 테이블을 결합한다. 한 테이블의 각 로우는 다른 테이블의
각각의 로우와 결합한다. Cartesian Products라고도 한다.

아래는 Cross Join 쿼리의 예제이다.

SELECT \* FROM T1, T2;

##### Inner Join

Inner Join은 일반적인 조인을 말하며, 두 테이블에서 조인 조건을 만족하는 로우들만
결합해서 반환한다.

아래는 Inner Join 쿼리의 예제이다.

SELECT \* FROM T1, T2 WHERE T1.i1 = T2.i1;

SELECT \* FROM T1 INNER JOIN T2 ON T1.i1 = T2.i1;

SELECT \* FROM T1, T2, T3 WHERE T1.i1 = T2.i1 AND T2.i1 \< T3.i2;

##### Outer Join

Outer Join은 두 개의 다른 테이블에서 조인 조건을 만족하는 로우를 판별해서
반환한다. Inner Join과 Outer Join의 차이점은 한 테이블에만 조인 조건을 만족하는
로우가 있고 다른 테이블에는 조인 조건을 만족하는 로우가 없는 경우, Inner Join은
해당 로우를 반환하지 않는 반면 Outer Join은 조인 조건을 만족하는 로우가 없는
테이블의 값을 NULL로 반환한다.

Outer Join은 다음 세 종류가 있다.

-   Left Outer Join

-   Right Outer Join

-   Full Outer Join

###### **Left Outer Join**

LEFT OUTER JOIN 키워드의 왼편에 테이블 A가, 오른편에 테이블 B가 있을 때, 조인
조건을 만족하는 A의 모든 로우가 반환된다. B에 만족하는 로우가 없는 경우에는
결과집합의 해당 자리에 NULL이 반환된다.

아래는 Left Outer Join 쿼리의 예제이다.

SELECT \* FROM A LEFT OUTER JOIN B ON A.c1 = B.c1;

SELECT \* FROM A, B WHERE A.c1 = B.c1(+);

###### **Right Outer Join**

RIGHT OUTER JOIN 키워드의 왼편에 테이블 A가, 오른편에 테이블 B가 있을 때, 조인
조건을 만족하는 B의 모든 로우가 반환된다. A에 만족하는 로우가 없는 경우에는
결과집합의 해당 자리에 NULL이 반환된다.

아래는 Right Outer Join 쿼리의 예제이다.

SELECT \* FROM A RIGHT OUTER JOIN B ON A.c1 = B.c1;

SELECT \* FROM A, B WHERE A.c1(+) = B.c1;

###### **Full Outer Join**

FULL OUTER JOIN 키워드의 왼편에 테이블 A가, 오른편에 테이블 B가 있을 때, A와 B
중 한 테이블에만 조인 조건을 만족하는 로우가 있어도 해당 로우가 반환된다. 조인
조건을 만족하는 로우가 없는 테이블에 대해서는 결과집합의 해당 자리에 NULL이
반환된다.

아래는 Full Outer Join 쿼리의 예제이다.

SELECT \* FROM A FULL OUTER JOIN B ON A.c1 = B.c1;

##### Semi Join

테이블 A와 테이블 B를 Semi Join하는 경우, B에 존재하는 A의 모든 로우를 반환한다.
A의 한 로우에 대해서 B의 여러 로우가 일치하더라도 한 로우만 반환된다.

아래는 Semi Join 쿼리의 예제이다.

SELECT \* FROM T1 WHERE EXISTS ( SELECT i1 FROM T2 WHERE T1.i1 = T2.i1 );

SELECT \* FROM T1 WHERE i1 IN ( SELECT i1 FROM T2 );

##### Anti Join

테이블 A와 테이블 B를 Anti Join하는 경우, B에 존재하지 않는 A의 로우들만
반환한다.

SELECT \* FROM T1 WHERE NOT EXISTS ( SELECT i1 FROM T2 WHERE T1.i1 = T2.i1 );

SELECT \* FROM T1 WHERE i1 NOT IN ( SELECT i1 FROM T2 );

##### 예제

위에서 설명한 각 조인의 실행 결과를 보여주기 위해 employee와 dept 테이블을
생생한다.

CREATE TABLE employee(name VARCHAR(10), empid INTEGER, deptname VARCHAR(20));

CREATE TABLE dept(deptname VARCHAR(20), manager VARCHAR(10));

INSERT INTO employee VALUES('Harry', 3415, 'Finance');

INSERT INTO employee VALUES('Sally', 2241, 'Sales');

INSERT INTO employee VALUES('George', 3401, 'Finance');

INSERT INTO employee VALUES('Harriet', 2202, 'Production');

INSERT INTO dept VALUES('Sales','Bob');

INSERT INTO dept VALUES('Sales','Thomas');

INSERT INTO dept VALUES('Production','Katie');

INSERT INTO dept VALUES('Production','Mark');

아래는 Cross Join 쿼리와 그 결과이다.

iSQL\> SELECT \* FROM employee, dept;

NAME EMPID DEPTNAME DEPTNAME MANAGER

\--------------------------------------------------------------------------------------

Harry 3415 Finance Sales Bob

Harry 3415 Finance Sales Thomas

Harry 3415 Finance Production Katie

Harry 3415 Finance Production Mark

Sally 2241 Sales Sales Bob

Sally 2241 Sales Sales Thomas

Sally 2241 Sales Production Katie

Sally 2241 Sales Production Mark

George 3401 Finance Sales Bob

George 3401 Finance Sales Thomas

George 3401 Finance Production Katie

George 3401 Finance Production Mark

Harriet 2202 Production Sales Bob

Harriet 2202 Production Sales Thomas

Harriet 2202 Production Production Katie

Harriet 2202 Production Production Mark

16 rows selected.

아래는 Inner Join 쿼리와 그 결과이다.

iSQL\> SELECT \* FROM employee A, dept B WHERE A.deptname = B.deptname;

NAME EMPID DEPTNAME DEPTNAME MANAGER

\--------------------------------------------------------------------------------------

Sally 2241 Sales Sales Thomas

Sally 2241 Sales Sales Bob

Harriet 2202 Production Production Mark

Harriet 2202 Production Production Katie

4 rows selected.

아래는 Left Outer Join 쿼리와 그 결과이다.

iSQL\> SELECT \* FROM employee A LEFT OUTER JOIN dept B ON A.deptname =
B.deptname;

NAME EMPID DEPTNAME DEPTNAME MANAGER

\--------------------------------------------------------------------------------------

Harry 3415 Finance

Sally 2241 Sales Sales Thomas

Sally 2241 Sales Sales Bob

George 3401 Finance

Harriet 2202 Production Production Mark

Harriet 2202 Production Production Katie

6 rows selected.

아래는 Right Outer Join 쿼리와 그 결과이다.

iSQL\> SELECT \* FROM employee A RIGHT OUTER JOIN dept B ON A.deptname =
B.deptname;

NAME EMPID DEPTNAME DEPTNAME MANAGER

\--------------------------------------------------------------------------------------

Sally 2241 Sales Sales Bob

Sally 2241 Sales Sales Thomas

Harriet 2202 Production Production Katie

Harriet 2202 Production Production Mark

4 rows selected.

아래는 Semi Outer Join 쿼리와 그 결과이다.

iSQL\> SELECT \* FROM employee A WHERE EXISTS ( SELECT deptname FROM dept B
WHERE A.deptname = B.deptname );

NAME EMPID DEPTNAME

\--------------------------------------------------

Sally 2241 Sales

Harriet 2202 Production

2 rows selected.

아래는 Anti Outer Join 쿼리와 그 결과이다.

iSQL\> SELECT \* FROM employee A WHERE NOT EXISTS ( SELECT deptname FROM dept B
WHERE A.deptname = B.deptname );

NAME EMPID DEPTNAME

\--------------------------------------------------

Harry 3415 Finance

George 3401 Finance

2 rows selected.

#### HINTS 절

힌트의 문법과 자세한 설명은 "[힌트 구문](#hint_syntax)"과 "[힌트
목록](#힌트-목록)"을 참고하기 바란다.

#### 제약사항

Altibase는 SQL질의 및 저장프로시저 수행에 있어 다음과 같은 제약을 가진다.

-   최대 65536개까지의 내부 튜플[^7]만 질의 처리에 사용될 수 있다.

    [^7]: 내부 튜플(internal tuple)은 알티베이스가 질의 처리를 위해 할당하는
    메모리의 단위이다

-   FROM절에에 최대 32개 까지의 테이블 또는 뷰를 사용할 수 있다.

-   WHERE, GROUP BY, ORDER BY 같은 연산식이 사용 가능한 절에 최대 32개까지의
    테이블 또는 뷰를 사용할 수 있다.

위와 같은 제약을 위배하게 되면 다음과 같은 에러가 발생하게 된다.

-   qpERR_ABORT_QTC_TUPLE_SHORTAGE  
    : There are too many DML statements in the stored procedure, or the SQL
    query is too long.

-   qpERR_ABORT_QTC_TOO_MANY_TABLES  
    : Too many tables are referenced in a phrase.

#### 예제

##### 단순 조회

\<질의\> 모든 사원의 이름, 고용일, 월급을 검색하라.

iSQL\> SELECT e_firstname, e_lastname, join_date, salary

FROM employees;

E_FIRSTNAME E_LASTNAME JOIN_DATE SALARY

\-----------------------------------------------------------------------

Chan-seung Moon

Susan Davenport 18-NOV-2009 1500

Ken Kobain 11-JAN-2010 2000

.

.

.

20 rows selected.

\<질의\> 급여가 가장 많은 사원의 이름, 고용일, 월급을 검색하라.

iSQL\> SELECT TOP (1) e_firstname, e_lastname, join_date, salary

2 FROM employees ORDER BY salary;

E_FIRSTNAME E_LASTNAME JOIN_DATE SALARY

\--------------------------------------------------------------------------

Gottlieb Fleischer 24-JAN-2004 500

1 row selected.

\<질의\> FROM절 이하가 생략된 쿼리의 예제이다.

iSQL\> SELECT cos(0), 256;

COS(0) 256

\--------------------------------------

1 256

1 row selected.

\<질의\> 현재 날짜와 departments 테이블의 모든 칼럼 값을 검색하라.

iSQL\> SELECT sysdate, \*

FROM departments;

SYSDATE DNO DNAME DEP_LOCATION MGR_NO

\--------------------------------------------------------------------------------------------

26-JUN-2013 1001 RESEARCH DEVELOPMENT DEPT 1 New York 16

26-JUN-2013 1002 RESEARCH DEVELOPMENT DEPT 2 Sydney 13

26-JUN-2013 1003 SOLUTION DEVELOPMENT DEPT Osaka 14

26-JUN-2013 2001 QUALITY ASSURANCE DEPT Seoul 17

26-JUN-2013 3001 CUSTOMERS SUPPORT DEPT London 4

26-JUN-2013 3002 PRESALES DEPT Peking 5

26-JUN-2013 4001 MARKETING DEPT Brasilia 8

26-JUN-2013 4002 BUSINESS DEPT Palo Alto 7

8 rows selected.

##### WITH subquery 절 사용

\<질의\> dept_costs와 avg_cost라는 쿼리 이름을 생성하여 주 질의에서 이들 이름을
사용한다.

iSQL\> WITH

2 dept_costs AS (

3 SELECT DNAME, SUM(salary) dept_total

4 FROM employees e, departments d

5 WHERE e.dno = d.dno

6 GROUP BY DNAME),

7 avg_cost AS (

8 SELECT SUM(dept_total)/COUNT(\*) avg

9 FROM dept_costs)

10 SELECT \* FROM dept_costs

11 WHERE dept_total \> (SELECT avg FROM avg_cost)

12 ORDER BY DNAME;

DEPT_COSTS.DNAME DEPT_COSTS.DEPT_TOTAL

\---------------------------------------------------------

BUSINESS DEPT 4190

RESEARCH DEVELOPMENT DEPT 1 4300

SOLUTION DEVELOPMENT DEPT 9753

3 rows selected.

##### 파티션을 사용한 조회

CREATE TABLE T1 (I1 INTEGER)

PARTITION BY RANGE (I1)

(

PARTITION P1 VALUES LESS THAN (100),

PARTITION P2 VALUES LESS THAN (200),

PARTITION P3 VALUES DEFAULT

) TABLESPACE SYS_TBS_DISK_DATA;

INSERT INTO T1 VALUES (55);

INSERT INTO T1 VALUES (123);

SELECT \* FROM T1 PARTITION (P1);

I1

\----------

55

SELECT \* FROM T1 PARTITION (P2);

I1

\----------

123

SELECT \* FROM T1 PARTITION (P3);

No rows selected.

##### 검색 조건 사용

\<질의\> 월급이 100만원 이하인 직원의 이름, 업무, 입사일, 월급을 월급 순서로
정렬하라.

iSQL\> SELECT e_firstname, e_lastname, emp_job, salary

FROM employees

WHERE salary \< 1500

ORDER BY 4 DESC;

E_FIRSTNAME E_LASTNAME EMP_JOB SALARY

\------------------------------------------------------------------------

Takahiro Fubuki PM 1400

Curtis Diaz planner 1200

Jason Davenport webmaster 1000

Mitch Jones PM 980

Gottlieb Fleischer manager 500

5 rows selected.

##### Hierachical query 사용 검색

\<질의\> id 열의 값이 0인 행을 루트로 하는 행들을 얻기 위한 계층적 질의문은
다음과 같다.

iSQL\> CREATE TABLE hier_order(id INTEGER, parent INTEGER);

Create success.

iSQL\> INSERT INTO hier_order VALUES(0, NULL);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(1, 0);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(2, 1);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(3, 1);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(4, 1);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(5, 0);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(6, 0);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(7, 6);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(8, 7);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(9, 7);

1 row inserted.

iSQL\> INSERT INTO hier_order VALUES(10, 6);

1 row inserted.

iSQL\> SELECT ID, parent, LEVEL

FROM hier_order START WITH id = 0 CONNECT BY PRIOR id = parent ORDER BY level;

ID PARENT LEVEL

\------------------------------------------------

0 1

6 0 2

5 0 2

1 0 2

10 6 3

4 1 3

7 6 3

3 1 3

2 1 3

8 7 4

9 7 4

11 rows selected.

[그림 4‑1] 계층적 구조 데이터

\<질의\> START WITH 절을 생략하여 테이블 내의 모든 행을 루트 행으로 사용하고
PRIOR id = parent 조건을 만족하는 질의이다.

iSQL\> SELECT id, parent, level

FROM hier_order CONNECT BY PRIOR id = parent ORDER BY id;

ID PARENT LEVEL

\------------------------------------------------

0 1

1 0 1

1 0 2

2 1 1

2 1 3

2 1 2

3 1 2

3 1 1

3 1 3

4 1 1

4 1 2

4 1 3

5 0 1

5 0 2

6 0 2

6 0 1

7 6 1

7 6 2

7 6 3

8 7 3

8 7 1

8 7 2

8 7 4

9 7 2

9 7 3

9 7 4

9 7 1

10 6 1

10 6 2

10 6 3

30 rows selected.

\<질의\> 다음 계층적 질의문은 순환을 형성하는 행을 제외한 결과 집합을 얻기
위하여 IGNORE LOOP 절을 사용한 예이다.

iSQL\> CREATE TABLE triple(

num INTEGER,

tri INTEGER,

PRIMARY KEY(num, tri));

Create success.

iSQL\> CREATE OR REPLACE PROCEDURE proc_tri

AS

v1 INTEGER;

BEGIN

FOR v1 IN 1 .. 1000

INSERT INTO triple VALUES(v1, v1 \* 3);

END ;

INSERT INTO triple VALUES(1, 1);

END;

/

Create success.

iSQL\> EXEC proc_tri;

Execute success.

iSQL\> SELECT num, tri, level

FROM triple

WHERE num \< 3001

START WITH num = 1

CONNECT BY PRIOR tri = num

IGNORE ;

NUM TRI LEVEL

\------------------------------------------------

1 1 1

1 3 2

3 9 3

9 27 4

27 81 5

81 243 6

243 729 7

729 2187 8

1 3 1

3 9 2

9 27 3

27 81 4

81 243 5

243 729 6

729 2187 7

15 rows selected.

\<질의\> 계층적 질의에서 CONNECT_BY_ROOT 연산자를 사용해서 각 id의 루트 노드를
구하라.

CREATE TABLE hier_order(id INTEGER, name varchar(10), parent INTEGER);

INSERT INTO hier_order VALUES(0, 'Moon', NULL);

INSERT INTO hier_order VALUES(1, 'Davenport', 0);

INSERT INTO hier_order VALUES(2, 'Kobain', 1);

INSERT INTO hier_order VALUES(3, 'Foster', 1);

INSERT INTO hier_order VALUES(4, 'Ghorbani', 1);

INSERT INTO hier_order VALUES(5, 'Momoi', 0);

INSERT INTO hier_order VALUES(6, 'Fleischer', 0);

INSERT INTO hier_order VALUES(7, 'Wang', 6);

INSERT INTO hier_order VALUES(8, 'Diaz', 7);

INSERT INTO hier_order VALUES(9, 'Liu', 7);

INSERT INTO hier_order VALUES(10, 'Hammond', 6);

iSQL\> SELECT id, CONNECT_BY_ROOT id "Root_Id"

FROM hier_order

WHERE LEVEL \> 1

START WITH id = 0

CONNECT BY PRIOR id = parent

ORDER BY id, "Root_Id";

ID Root_Id

\---------------------------

1 0

2 0

3 0

4 0

5 0

6 0

7 0

8 0

9 0

10 0

10 rows selected.

\<질의\> 계층적 질의에서 CONNECT_BY_ISLEAF 의사 칼럼을 사용해서 각 행이 리프
노드인지 여부를 구하라.

iSQL\> SELECT id, CONNECT_BY_ISLEAF "IsLeaf",

LEVEL

FROM hier_order

START WITH id = 0

CONNECT BY PRIOR id = parent

ORDER BY id, "IsLeaf";

ID IsLeaf LEVEL

\----------------------------------------------------------

0 0 1

1 0 2

2 1 3

3 1 3

4 1 3

5 1 2

6 0 2

7 0 3

8 1 4

9 1 4

10 1 3

11 rows selected.

\<질의\> ORDER SIBLINGS BY를 사용해서 계층 구조를 보존하면서, name을 기준으로
정렬하라.

iSQL\> SELECT name, id, parent, LEVEL

FROM hier_order

START WITH id = 0

CONNECT BY PRIOR id = parent

ORDER SIBLINGS BY name;

NAME ID PARENT LEVEL

\--------------------------------------------------------------

Moon 0 1

Davenport 1 0 2

Foster 3 1 3

Ghorbani 4 1 3

Kobain 2 1 3

Fleischer 6 0 2

Hammond 10 6 3

Wang 7 6 3

Diaz 8 7 4

Liu 9 7 4

Momoi 5 0 2

11 rows selected.

##### Recursive query 검색

\<질의\> id 열의 값이 0인 행을 루트로 하는 행들을 얻기 위한 계층적 질의문은
다음과 같다. (순환 데이타)

iSQL\> INSERT INTO hier_order VALUES(7, 9);

1 row inserted.

iSQL\> WITH q1 (q1_i1,q1_i2, lvl) as

2 (

3 SELECT id,parent,1 FROM hier_order WHERE id = 0

4 UNION ALL

5 SELECT a.id,a.parent,lvl+1 from hier_order a, q1 b where a.parent = b.q1_i1

6 )

7 select \* from q1 limit 18;

Q1_I1 Q1_I2 LVL

\----------------------------------------

0 1

1 0 2

5 0 2

6 0 2

2 1 3

3 1 3

4 1 3

7 6 3

10 6 3

8 7 4

9 7 4

7 9 5

8 7 6

9 7 6

7 9 7

8 7 8

9 7 8

7 9 9

18 rows selected.

##### GROUP BY를 이용한 조회

\<질의\> 부서별 급여 평균을 계산하라.

iSQL\> SELECT dno, AVG(salary) AS avg_sal

FROM employees

GROUP BY dno;

DNO AVG_SAL

\---------------------------

1001 2150

1002 1340

1003 2438.25

2001 1400

3001 1800

3002 2500

4001 1550

4002 1396.66667

1500

9 rows selected.

-   SELECT 목록의 열 중 집계 함수가 사용되지 않은 모든 열은 GROUP BY 절에 있어야
    한다.

-   칼럼에 별명을 주거나, 칼럼 이름과 다른 별명을 사용하고 싶으면 위의 AS
    avg_sal 처럼 칼럼의 이름 뒤에 사용하고 싶은 별명을 적어주면 된다. 칼럼
    별명을 만들 때 AS 키워드는 생략 가능하다.

-   하이픈 두개 (“--“)가 오면 그 줄의 이후 부분은 모두 주석(comment) 으로
    처리된다.

\<질의\> 여러 열에 GROUP BY 절을 사용해서 각 부서내에서 각 직위별로 지급되는
급여 총액을 출력하라.

iSQL\> SELECT dno, emp_job, COUNT(emp_job) num_emp, SUM(salary) sum_sal

FROM employees

GROUP BY dno, emp_job;

DNO EMP_JOB NUM_EMP SUM_SAL

\-------------------------------------------------------------------

3002 CEO 1

designer 1 1500

1001 engineer 1 2000

3001 PL 1 1800

3002 PL 1 2500

1002 programmer 1 1700

4002 manager 1 500

4001 manager 1

4001 planner 2 3100

1003 programmer 1 4000

1003 webmaster 2 3750

4002 sales rep 3 3690

1002 PM 1 980

1003 PM 1 2003

1001 manager 1 2300

2001 PM 1 1400

16 rows selected.

\<질의\> 평균 급여가 \$1500 USD를 넘는 부서의 평균 급여를 출력하라.

iSQL\> SELECT dno, AVG(salary)

FROM employees

WHERE AVG(salary) \> 1500

GROUP BY dno;

[ERR-31061 : An aggregate function is not allowed here.

0003 : WHERE AVG(SALARY) \> 1500000

\^ \^

]

\<질의\> HAVING 절을 사용하여 위의 오류를 수정할 수 있다.

iSQL\> SELECT dno, AVG(salary)

FROM employees

GROUP BY dno

HAVING AVG(salary) \> 1500;

DNO AVG(SALARY)

\---------------------------

1001 2150

1003 2438.25

3001 1800

3002 2500

4001 1550

5 rows selected.

\<질의\> 3개 이상 주문된 상품번호와 그 상품들의 총 수를 출력하라.

iSQL\> SELECT gno, COUNT(\*)

FROM orders

GROUP BY gno

HAVING COUNT(\*) \> 2;

GNO COUNT

\------------------------------------

A111100002 3

C111100001 4

D111100008 3

E111100012 3

4 rows selected.

\<질의\> 12월 한 달 동안 2개 이상 주문된 상품번호와 그 상품들의 평균 주문양을
평균 주문양 순서대로 출력하라.

iSQL\> SELECT gno, AVG(qty) month_avg

FROM orders

WHERE order_date BETWEEN '01-Dec-2011' AND '31-Dec-2011'

GROUP BY gno

HAVING COUNT(\*) \> 1

ORDER BY AVG(qty);

GNO MONTH_AVG

\---------------------------

A111100002 35

D111100003 300

D111100004 750

C111100001 1637.5

D111100010 1750

D111100002 1750

E111100012 4233.33333

D111100008 5500

8 rows selected.

\<질의\> GROUP BY절에 ROLLUP을 사용해서 다음 세 조합에 대해 급여의 소계를
구한다: (dno, sex), (dno), (총계).

iSQL\> select dno, sex, sum(SALARY) from employees group by rollup( dno, sex);

DNO SEX SUM(SALARY)

\---------------------------------

1001 F 2300

1001 M 2000

1001 4300

1002 M 2680

1002 2680

1003 F 4000

1003 M 5753

1003 9753

2001 M 1400

2001 1400

3001 M 1800

3001 1800

3002 M 2500

3002 2500

4001 M 3100

4001 3100

4002 F 1890

4002 M 2300

4002 4190

F 1500

1500

31223

22 rows selected.

\<질의\> GROUP BY절에 CUBE를 사용해서 그룹화 칼럼의 모든 조합에 대한 급여의
소계를 구한다: (dno, sex), (dno), (sex), (총계).

iSQL\> select dno, sex, sum(SALARY) from employees group by cube( dno, sex);

DNO SEX SUM(SALARY)

\---------------------------------

31223

1001 F 2300

1001 M 2000

1001 4300

1002 M 2680

1002 2680

1003 F 4000

1003 M 5753

1003 9753

2001 M 1400

2001 1400

3001 M 1800

3001 1800

3002 M 2500

3002 2500

4001 M 3100

4001 3100

4002 F 1890

4002 M 2300

4002 4190

F 1500

1500

F 9690

M 21533

24 rows selected.

\<질의\> GROUP BY 절에 GROUPING SETS를 사용해서 다음의 세 그룹화에 대해 급여
소계를 구하라: (dno,sex), (dno), ()

iSQL\> SELECT dno, sex, SUM(salary)

FROM employees

GROUP BY GROUPING SETS( (dno, sex), dno, () );

DNO SEX SUM(SALARY)

\---------------------------------

3002 M 2500

F 1500

1001 M 2000

3001 M 1800

1002 M 2680

4002 M 2300

4001 M 3100

1003 F 4000

1003 M 5753

4002 F 1890

1001 F 2300

2001 M 1400

3002 2500

1500

1001 4300

3001 1800

1002 2680

4002 4190

4001 3100

1003 9753

2001 1400

31223

22 rows selected.

##### ORDER BY를 이용한 조회

\<질의\> 모든 사원의 이름, 부서 번호 및 급여를 부서 번호를 기준으로 정렬한 후
급여를 기준으로 해서 내림차순으로 출력하라.

iSQL\> SELECT e_firstname, e_lastname, dno, salary

FROM employees

ORDER BY dno, salary DESC;

E_FIRSTNAME E_LASTNAME DNO SALARY

\-------------------------------------------------------------------------

Wei-Wei Chen 1001 2300

Ken Kobain 1001 2000

Ryu Momoi 1002 1700

Mitch Jones 1002 980

Elizabeth Bae 1003 4000

.

.

.

20 rows selected.

\<질의\> 다음은 모든 사원의 이름 및 급여를 부서 번호를 기준으로 정렬한 후 급여를
기준으로 해서 내림차순으로 출력하는 질의이다. (SELECT 목록에 없는 열을 기준으로
정렬할 수도 있다.)

iSQL\> SELECT e_firstname, e_lastname, salary

FROM employees

ORDER BY dno, salary DESC;

E_FIRSTNAME E_LASTNAME SALARY

\------------------------------------------------------------

Wei-Wei Chen 2300

Ken Kobain 2000

Ryu Momoi 1700

Mitch Jones 980

Elizabeth Bae 4000

.

.

.

20 rows selected.

##### 연산자 사용 조회

\<질의\> 재고 상품의 이름, 각 제품의 재고 값을 출력하라.

iSQL\> SELECT gname, (stock\*price) inventory_value

FROM goods;

GNAME INVENTORY_VALUE

\-------------------------------------

IM-300 78000000

IM-310 9800000

NT-H5000 27924000

.

.

.

30 rows selected.

##### 별명(alias_name)을 사용한 조회

\<질의\> 부서 위치에 별명(지역명)을 지정하여 검색하라.

iSQL\> SELECT dname, 'District Name', dep_location location

FROM departments;

DNAME 'District Name' LOCATION

\------------------------------------------------

Applied Technology Team District Name Mapo

Engine Development Team District Name Yeoido

Marketing Team District Name Gangnam

Planning & Management Team District Name Gangnam

Sales Team District Name Shinchon

5 rows selected.

##### LIMIT절을 사용한 조회

\<질의\> employees테이블에서 사원 이름을 3번째 레코드 부터 5명만 출력하라.

iSQL\> SELECT e_firstname first_name, e_lastname last_name

FROM employees

LIMIT 3, 5;

FIRST_NAME LAST_NAME

\-----------------------------------------------

Ken Kobain

Aaron Foster

Farhad Ghorbani

Ryu Momoi

Gottlieb Fleischer

5 rows selected.

\<질의\> 관리자 테이블에서 첫 번째 레코드에 해당하는 사원의 이름과 급여를
출력하라.

iSQL\> CREATE TABLE managers(

mgr_no INTEGER PRIMARY KEY,

m_lastname VARCHAR(20),

m_firstname VARCHAR(20),

address VARCHAR(60));

Create success.

iSQL\> INSERT INTO managers VALUES(7, 'Fleischer', 'Gottlieb', '44-25
YouIDo-dong Youngdungpo-gu Seoul Korea');

1 row inserted.

iSQL\> INSERT INTO managers VALUES(8, 'Wang', 'Xiong', '3101 N Wabash Ave
Brooklyn NY');

1 row inserted.

iSQL\> INSERT INTO managers VALUES(12, 'Hammond', 'Sandra', '130 Gongpyeongno
Jung-gu Daegu Korea');

1 row inserted.

iSQL\> SELECT e_firstname, e_lastname, salary FROM employees WHERE eno = (SELECT
mgr_no FROM managers LIMIT 1);

E_FIRSTNAME E_LASTNAME SALARY

\------------------------------------------------------------

Gottlieb Fleischer 500

1 row selected.

##### FOR UPDATE를 사용한 조회

| Transaction A                                                                                                                                                                                                                                  | Time Point | Transaction B                                                                                                                                       |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| iSQL\> AUTOCOMMIT OFF; Set autocommit off success.                                                                                                                                                                                             |            | iSQL\> AUTOCOMMIT OFF; Set autocommit off success.                                                                                                  |
| (request X lock on employees) iSQL\> LOCK TABLE employees IN EXCLUSIVE MODE; Lock success. (acquire X lock on employees) iSQL\> SELECT e_lastname FROM employees WHERE eno = 15; E_LASTNAME ------------------------ Davenport 1 row selected. | 1          |                                                                                                                                                     |
|                                                                                                                                                                                                                                                | 2          | iSQL\> SELECT e_lastname FROM employees WHERE eno = 15 FOR UPDATE; (request conflicts with the X lock already held by transaction A) wait wait wait |
| iSQL\> UPDATE employees SET ENO = 30 WHERE eno = 15; 1 row updated. iSQL\> SELECT e_lastname FROM employees WHERE eno = 30; E_LASTNAME ------------------------ Davenport 1 row selected.                                                      | 3          |                                                                                                                                                     |
| iSQL\> COMMIT; Commit success.                                                                                                                                                                                                                 | 4          |                                                                                                                                                     |
|                                                                                                                                                                                                                                                | 5          | (resume) E_LASTNAME ------------------------ No rows selected.                                                                                      |

##### HINTS를 사용한 조회

###### **Table Access Method Hints**

\- full scan, index scan, index ascending order scan, index descending order
scan, no index scan

다음은 사원들 중 모든 여사원의 번호, 이름, 직업을 검색하는 질의이다.

SELECT eno, e_firstname, e_lastname, emp_job FROM employees WHERE sex = 'F';

예를 들어, 많은 수의 사원들이 있는 사원 테이블의 성별(SEX) 칼럼에 인덱스가
정의되어 있고, 이 칼럼의 값은 ‘M’ 또는 ‘F’이다.

만약, 남자 직원과 여자 직원의 비율이 같다면 full scan으로 전체 테이블을 검색하는
것이 index scan으로 검색하는 것보다 더 빠를 것이다. 그러나, 만약 여자 직원의
비율이 남자 직원보다 상대적으로 적다면, index scan이 전체 테이블의 full scan
보다 빠를 것이다. 즉, 칼럼이 서로 다른 두 개의 값만을 가지고 있을 때, 쿼리
옵티마이저는 각 값의 행들이 50%씩 존재한다고 가정해서 비용 기반 접근 방식으로서
index scan 보다 전체 테이블의 full scan을 선택한다.

아래의 질의들에서 access 회수를 비교해 보면 각각 20과 4인 것을 알수 있다.

\<질의\> 성별이 여자인 직원의 사원 번호, 이름, 직업을 출력하라. (full scan 이용)

iSQL\> SELECT /\*+ FULL SCAN(employees) \*/ eno, e_firstname, e_lastname,
emp_job

FROM employees

WHERE sex = 'F';

ENO E_FIRSTNAME E_LASTNAME EMP_JOB

\------------------------------------------------

.

.

.

\------------------------------------------------

PROJECT ( COLUMN_COUNT: 4, TUPLE_SIZE: 65 )

SCAN ( TABLE: EMPLOYEES, FULL SCAN, ACCESS: 20, SELF_ID: 2 )

\------------------------------------------------

\<질의\> 성별이 여자인 직원의 사원 번호, 이름, 직업을 출력하라. (index 이용)

iSQL\> CREATE INDEX gender_index ON employees(sex);

Create success.

iSQL\> SELECT /\*+ INDEX(employees, gender_INDEX) use gender_index because there
are few female employees \*/ eno, e_firstname, e_lastname, emp_job

FROM employees

WHERE sex = 'F';

ENO E_FIRSTNAME E_LASTNAME EMP_JOB

\------------------------------------------------

.

.

.

\------------------------------------------------

PROJECT ( COLUMN_COUNT: 4, TUPLE_SIZE: 65 )

SCAN ( TABLE: EMPLOYEES, INDEX: GENDER_INDEX, ACCESS: 4, SELF_ID: 2 )

\------------------------------------------------

\<질의\> 1사분기(1월에서 3월까지) 동안의 모든 주문에 대한 주문번호, 상품번호,
주문량을 출력하라 (index 이용). 각 월에 해당하는 주문 테이블의 이름이
orders_\#\# 라고 가정한다.

create view orders as

select ono, order_date, eno, cno, gno, qty from orders_01

union all

select ono, order_date, eno, cno, gno, qty from orders_02

union all

select ono, order_date, eno, cno, gno, qty from orders_03;

create index order1_gno on orders_01(gno);

create index order2_gno on orders_02(gno);

create index order3_gno on orders_03(gno);

iSQL\> select /\*+ index( orders,

orders1_gno, orders2_gno,orders3_gno ) \*/

ONO, GNO, QTY

from orders;

ONO GNO QTY

\-------------------------------------------------

.

.

.

\------------------------------------------------

PROJECT ( COLUMN_COUNT: 3, TUPLE_SIZE: 24 )

VIEW ( ORDERS, ACCESS: 14, SELF_ID: 6 )

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

VIEW ( ACCESS: 14, SELF_ID: 5 )

BAG-UNION

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

SCAN ( TABLE: ORDERS_01, INDEX: ORDERS1_GNO, ACCESS: , SELF_ID: 0 )

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

SCAN ( TABLE: ORDERS_02, INDEX: ORDERS2_GNO, ACCESS: 4, SELF_ID: 1 )

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

SCAN ( TABLE: ORDERS_03, INDEX: ORDERS3_GNO, ACCESS: 7, SELF_ID: 4 )

\------------------------------------------------

###### **Join Order Hints (ordered, optimized)**

\<질의\> 주문된 상품을 담당하고 있는 직원의 사원번호, 이름과 해당 고객의 이름을
출력하라. (employees 테이블과 customers 테이블을 조인하고, 그 결과를 orders
테이블과 조인하기 위해 ORDERED 힌트를 사용하라.)

iSQL\> SELECT /\*+ ORDERED \*/ DISTINCT o.eno, e.e_lastname, c.c_lastname

FROM employees e, customers c, orders o

WHERE e.eno = o.eno AND o.cno = c.cno;

ENO E_LASTNAME C_LASTNAME

\------------------------------------------------

.

.

.

\------------------------------------------------

PROJECT ( COLUMN_COUNT: 3, TUPLE_SIZE: 48 )

DISTINCT ( ITEM_SIZE: 40, ITEM_COUNT: 21, BUCKET_COUNT: 1024, ACCESS: 21,
SELF_ID: 4, REF_ID: 3 )

JOIN

JOIN

SCAN ( TABLE: EMPLOYEES E, FULL SCAN, ACCESS: 20, SELF_ID: 1 )

SCAN ( TABLE: CUSTOMERS C, FULL SCAN, ACCESS: 400, SELF_ID: 2 )

SCAN ( TABLE: ORDERS O, FULL SCAN, ACCESS: 12000, SELF_ID: 3 )

\------------------------------------------------

\<질의\> 주문된 상품을 담당하고 있는 직원의 사원번호, 이름과 해당 고객의 이름을
출력하라. (FROM 절의 테이블들의 순서에 상관없이 옵티마이저에 의해서 테이블 조인
순서가 결정되도록 하라.)

iSQL\> SELECT DISTINCT o.eno, e.e_lastname, c.c_lastname

FROM employees e, customers c, orders o

WHERE e.eno = o.eno AND o.cno = c.cno;

ENO E_LASTNAME C_LASTNAME

\------------------------------------------------

.

.

.

\------------------------------------------------

PROJECT ( COLUMN_COUNT: 3, TUPLE_SIZE: 48 )

DISTINCT ( ITEM_SIZE: 40, ITEM_COUNT: 21, BUCKET_COUNT: 1024, ACCESS: 21,
SELF_ID: 4, REF_ID: 1 )

JOIN

JOIN

SCAN ( TABLE: CUSTOMERS C, FULL SCAN, ACCESS: 20, SELF_ID: 2 )

SCAN ( TABLE: ORDERS O, INDEX: ODR_IDX2, ACCESS: 30, SELF_ID: 3 )

SCAN ( TABLE: EMPLOYEES E, INDEX: \__SYS_IDX_ID_366, ACCESS: 30, SELF_ID: 1 )

\------------------------------------------------

###### **Optimizer Mode Hints (rule, cost)**

iSQL\> SELECT /\*+ RULE \*/ \* FROM t1, t2 WHERE t1.i1 = t2.i1;

iSQL\> SELECT /\*+ COST \*/ \* FROM t1, t2 WHERE t1.i1 = t2.i1;

###### **Normal Form Hints (CNF, DNF)**

iSQL\> SELECT /\*+ CNF \*/ \* FROM t1 WHERE i1 = 1 OR i1 = 2;

iSQL\> SELECT /\*+ DNF \*/ \* FROM t1 WHERE i1 = 1 OR i1 = 2;

###### **Join Method Hints (nested loop, hash, sort, sort merge)**

iSQL\> SELECT /\*+ USE_NL (t1,t2) \*/ \* FROM t1, t2 WHERE t1.i1 = t2.i1;

iSQL\> SELECT /\*+ USE_HASH (t1,t2) \*/ \* FROM t1, t2 WHERE t1.i1 = t2.i1;

iSQL\> SELECT /\*+ USE_SORT (t1,t2) \*/ \* FROM t1, t2 WHERE t1.i1 = t2.i1;

iSQL\> SELECT /\*+ USE_MERGE (t1,t2) \*/ \* FROM t1, t2 WHERE t1.i1 = t2.i1;

###### **Hash Bucket Size Hints (hash bucket count, group bucket count, set bucket count)**

iSQL\> SELECT /\*+ HASH BUCKET COUNT (20) \*/ DISTINCT \* FROM t1;

iSQL\> SELECT \* FROM t1 GROUP BY i1, i2;

iSQL\> SELECT /\*+ GROUP BUCKET COUNT (20) \*/ \* FROM t1 GROUP BY i1, i2;

iSQL\> SELECT \* FROM t1 INTERSECT SELECT \* FROM t2;

iSQL\> SELECT /\*+ SET BUCKET COUNT (20) \*/ \* FROM t1 INTERSECT SELECT \* FROM
t2;

###### **Push Predicate Hints**

\<질의\> 1사분기(1월에서 3월까지) 동안 발생한 주문 중에서 한번의 주문수량이
10000개이상인 고객의 명단과 상품번호을 구하라.(고객 테이블과 주문 테이블을
조인하기 위해 Push Predicate 힌트를 사용하라.)

create view orders as

select ono, order_date, eno, cno, gno, qty from orders_01

union all

select ono, order_date, eno, cno, gno, qty from orders_02

union all

select ono, order_date, eno, cno, gno, qty from orders_03;

iSQL\> select /\*+ PUSH_PRED(orders) \*/ c_lastname, gno

2 from customers, orders

3 where customers.cno = orders.cno

4 and orders.qty \>= 10000;

C_LASTNAME GNO

\-------------------------------------

.

.

.

\------------------------------------------------

PROJECT ( COLUMN_COUNT: 2, TUPLE_SIZE: 34 )

JOIN

SCAN ( TABLE: CUSTOMERS, FULL SCAN, ACCESS: 20, SELF_ID: 2 )

FILTER

[ FILTER ]

AND

OR

ORDERS.QTY \>= 10000

VIEW ( ORDERS, ACCESS: 1, SELF_ID: 8 )

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

VIEW ( ACCESS: 1, SELF_ID: 7 )

BAG-UNION

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

SCAN ( TABLE: ORDERS_01, INDEX: ODR1_IDX2, ACCESS: 3, SELF_ID: 3 )

[ VARIABLE KEY ]

OR

AND

[ FILTER ]

AND

OR

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

SCAN ( TABLE: ORDERS_02, INDEX: ODR2_IDX2, ACCESS: 4, SELF_ID: 4 )

[ VARIABLE KEY ]

OR

AND

[ FILTER ]

AND

OR

PROJECT ( COLUMN_COUNT: 6, TUPLE_SIZE: 48 )

SCAN ( TABLE: ORDERS_03, INDEX: ODR3_IDX2, ACCESS: 7, SELF_ID: 6 )

[ VARIABLE KEY ]

OR

AND

[ FILTER ]

AND

OR

\------------------------------------------------

##### OUTER JOIN을 이용한 조회

\<질의\> 모든 부서에 대한 부서 번호와 사원 이름을 출력하라. (단, 사원이 전혀
없는 부서 번호 5001도 출력되게 하라.)

iSQL\> INSERT INTO departments VALUES('5001', 'Quality Assurance', 'Jonglo',
22);

1 row inserted.

iSQL\> SELECT d.dno, e.e_lastname

FROM departments d LEFT OUTER JOIN employees e ON d.dno = e.dno

ORDER BY d.dno;

DNO E_LASTNAME

\-------------------------------

.

5001

.

\<질의\> 모든 부서에 대한 부서 번호와 사원 이름을 출력하라. (단, 부서에 소속이
되어 있지 않은 CEO도 출력되게 하라.)

iSQL\> SELECT d.dno, e.e_lastname

FROM departments d RIGHT OUTER JOIN employees e ON d.dno = e.dno

ORDER BY d.dno;

DNO E_LASTNAME

\-------------------------------

.

Davenport

.

\<질의\> 부서의 위치와 상품을 모아 놓은 장소가 같은 곳에 해당하는 부서의
부서번호, 부서 이름, 상품 번호를 출력하라.

iSQL\> INSERT INTO departments VALUES('6002', 'headquarters', 'CE0002', 100);

1 row inserted.

iSQL\> SELECT d.dno, d.dname, g.gno

FROM departments d FULL OUTER JOIN goods g

ON d.dep_location = g.goods_location;

DNO DNAME GNO

\------------------------------------------------------------

.

6002 headquarters E111100005

.

##### In-line View를 이용한 조회

\<질의\> 자신이 속한 부서의 평균 급여보다 급여를 많이 받는 모든 사원의 이름,
급여, 부서 번호 및 그 부서의 평균 급여를 출력하라.

iSQL\> SELECT e.e_last name, e.salary, e.dno, v1.salavg

FROM employees e,

(SELECT dno, AVG(salary) salavg FROM employees GROUP BY dno) v1

WHERE e.dno = v1.dno

AND e.salary \> v1.salavg;

ENAME SALARY DNO SALAVG

\------------------------------------------------

.

.

.

##### Lateral View를 이용한 조회

\<질의\> 각 부서의 부서명과 급여 총계, 급여 평균을 검색하라.

iSQL\> SELECT DEPT.dname, LV.\*

FROM departments DEPT, LATERAL ( SELECT sum(salary), avg(salary)

FROM employees EMP WHERE DEPT.dno = EMP.dno ) LV;

DNAME SUM(SALARY) AVG(SALARY)

\-----------------------------------------------------------------------

RESEARCH DEVELOPMENT DEPT 1 4300 2150

RESEARCH DEVELOPMENT DEPT 2 2680 1340

SOLUTION DEVELOPMENT DEPT 9753 2438.25

QUALITY ASSURANCE DEPT 1400 1400

CUSTOMERS SUPPORT DEPT 1800 1800

PRESALES DEPT 2500 2500

MARKETING DEPT 3100 1550

BUSINESS DEPT 4190 1396.66666666667

8 rows selected.

\<질의\> 각 부서에서 사원 번호가 가장 빠른 사원 1인의 이름과 부서명을 검색하라.
부서에 사원이 없다면 부서명이라도 출력해야 한다.

insert into departments values(8000, 'empty dept', 'seoul', 20);

iSQL\> SELECT LV.e_firstname, LV.e_lastname, DEPT.dname

FROM departments DEPT OUTER APPLY ( SELECT TOP 1 e_firstname, e_lastname

FROM employees EMP WHERE DEPT.dno = EMP.dno ORDER BY eno ) LV;

E_FIRSTNAME E_LASTNAME DNAME

\--------------------------------------------------------------------------------

Ken Kobain RESEARCH DEVELOPMENT DEPT 1

Ryu Momoi RESEARCH DEVELOPMENT DEPT 2

Elizabeth Bae SOLUTION DEVELOPMENT DEPT

Takahiro Fubuki QUALITY ASSURANCE DEPT

Aaron Foster CUSTOMERS SUPPORT DEPT

Chan-seung Moon PRESALES DEPT

Xiong Wang MARKETING DEPT

Gottlieb Fleischer BUSINESS DEPT

empty dept

9 rows selected.

##### PIVOT/UNPIVOT 절을 이용한 조회

\<질의\> 각 부서별 남자와 여자 직원의 수를 구하라.

iSQL\> SELECT \* FROM

(SELECT d.dname, e.sex

FROM departments d, employees e

WHERE d.dno = e.dno)

PIVOT (COUNT(\*) FOR sex in ('M', 'F'))

ORDER BY dname;

DNAME 'M' 'F'

\----------------------------------------------------------------------

BUSINESS DEPT 3 1

CUSTOMERS SUPPORT DEPT 1 0

MARKETING DEPT 3 0

PRESALES DEPT 2 0

QUALITY ASSURANCE DEPT 1 0

RESEARCH DEVELOPMENT DEPT 1 1 1

RESEARCH DEVELOPMENT DEPT 2 2 0

SOLUTION DEVELOPMENT DEPT 3 1

8 rows selected.

\<질의\> 다음 예제는 비교를 위해서 GROUP BY와 ORDER BY 절을 이용한 질의를
보여준다. 같은 정보를 출력하지만, 읽기가 더 힘든 것을 알 수 있다.

iSQL\> SELECT d.dname, e.sex, count(\*) FROM departments d, employees e WHERE
d.dno = e.dno GROUP BY d.dname, e.sex ORDER BY d.dname, e.sex DESC;

DNAME SEX COUNT

\--------------------------------------------------------------

BUSINESS DEPT M 3

BUSINESS DEPT F 1

CUSTOMERS SUPPORT DEPT M 1

MARKETING DEPT M 3

PRESALES DEPT M 2

QUALITY ASSURANCE DEPT M 1

RESEARCH DEVELOPMENT DEPT 1 M 1

RESEARCH DEVELOPMENT DEPT 1 F 1

RESEARCH DEVELOPMENT DEPT 2 M 2

SOLUTION DEVELOPMENT DEPT M 3

SOLUTION DEVELOPMENT DEPT F 1

11 rows selected.

\<질의\> 사원의 전화번호와 성별이 각각 출력되도록 한다.

iSQL\> SELECT eno, e_lastname, e_firstname, "info", "item"

FROM employees

UNPIVOT ("info" FOR "item" IN (emp_tel as 'telno',

sex as 'sex'))

;

ENO E_LASTNAME E_FIRSTNAME info item

\------------------------------------------------------------------------

1 Moon Chan-seung 01195662365 telno

1 Moon Chan-seung M sex

2 Davenport Susan 0113654540 telno

2 Davenport Susan F sex

3 Kobain Ken 0162581369 telno

3 Kobain Ken M sex

4 Foster Aaron 0182563984 telno

4 Foster Aaron M sex

...

20 Blake William 01154112366 telno

20 Blake William M sex

40 rows selected.

##### Table Fuction 조회

\<질의\> 사용자 정의 함수 'func1'를 생성하여, 10개의 행을 검색하라.

iSQL\> CREATE TYPESET type1

AS

TYPE rec1 IS RECORD (c1 INTEGER, c2 INTEGER);

TYPE arr1 IS TABLE OF rec1 INDEX BY INTEGER;

END;

/

Create success.

iSQL\> CREATE FUNCTION func1(i1 INTEGER)

RETURN type1.arr1

AS

v1 type1.arr1;

BEGIN

for i in 1 .. i1 loop

v1[i].c1 := i;

v1[i].c2 := i \* i;

END LOOP;

RETURN v1;

END;

/

Create success.

iSQL\> SELECT \* FROM TABLE( func1(10) );

C1 C2

\---------------------------

1 1

2 4

3 9

4 16

5 25

6 36

7 49

8 64

9 81

10 100

10 rows selected.

### UPDATE 

#### 구문

update ::=

[hints ::=](#hints_diagram), [subquery ::=](#subquery), [set_clause_list
::=](#set_clause_list), [where_clause ::=](#update_where_clause),
[returning_clause ::=](#returning_clause), [limit_clause
::=](#update_limit_clause)

set_clause_list ::=

![](media/SQL/7184ad78375706045fb9afba82ebe65b.png)

*subquery ::=*

where_clause ::=

limit_clause ::=

#### 전제 조건

SYS 사용자, 테이블 소유자, UPDATE ANY TABLE 시스템 권한을 가진 사용자 및
테이블에 대한 UPDATE 객체 권한을 가진 사용자만이 이 구문으로 해당 테이블의
데이터를 갱신할 수 있다.

뷰의 레코드를 UPDATE할 때 사용자는 베이스 테이블에 대해서 위와 동일한 권한을
가져야 한다.

#### 설명

조건을 만족하는 레코드를 찾아 명시한 칼럼들의 값을 변경하는 구문이다.

파티션을 명시할 경우 해당 파티션에서 조건을 만족하는 레코드의 칼럼 값을
변경한다.

user_name

변경될 레코드가 속한 테이블의 소유자 이름을 명시한다. 생략하면 Altibase는
테이블이 현재 세션에 연결된 사용자의 스키마에 속한 것으로 간주한다.

tbl_name

변경될 레코드가 속한 테이블의 이름을 명시한다.

view_name

갱신될 뷰의 이름을 명시한다.

subquery

갱신 대상이 될 뷰를 서브쿼리로 명시한다.

set_clause_list

변경할 칼럼 이름과 값을 명시한다. 이 절에서 부질의를 사용할 수 있으며, 아래의
사항을 유의한다.

-   부질의는 한 개의 행만 반환해야 한다.

-   SET절에 명시된 칼럼의 개수와 검색 대상 칼럼의 개수가 동일해야 한다.

-   부질의에 대한 결과가 없으면 칼럼에 NULL이 갱신된다.

-   부질의를 사용할 때, 칼럼에 DEFAULT을 할당하면 칼럼의 DEFAULT 속성 값으로
    갱신된다.

TIMESTAMP 칼럼의 데이터 수정

TIMESTAMP 칼럼에 대해 UPDATE문 수행 시 기본적으로 칼럼 값이 시스템 시간 값으로
갱신된다. 따라서 TIMESTAMP 칼럼의 데이터 수정 시 값을 명시하지 않으면 널이 아닌
시스템 시간 값으로 변경된다.

TIMESTAMP 칼럼의 값을 시스템 시간으로 변경하는 또다른 방법은 칼럼 값에
DEFAULT키워드를 사용하는 것이다.

returning_clause

DELETE 구문의 returning_clause를 참고하라.

#### HINTS 옵션

힌트의 문법과 자세한 설명은 "[힌트 구문](#hint_syntax)"과 "[힌트
목록](#힌트-목록)"을 참고하기 바란다.

#### 주의 사항

SET 절에 같은 칼럼을 두번 이상 사용할 수 없다.

파티션 키 칼럼의 값이 수정되어 그 데이터가 포함된 레코드가 다른 파티션으로
이동해야 할 필요가 있을 경우, 파티션드 테이블이 ENABLE ROW MOVEMENT 옵션을
이용해서 생성되었거나 ALTER TABLE ENABLE ROW MOVEMENT 구문으로 테이블 속성이
변경되었다면 레코드가 자동으로 이동되지만, 그렇지 않을 때에는 에러가 발생한다.

널 제약조건이 있는 칼럼에 널을 삽입하거나 그 칼럼의 값을 널로 변경할 수 없다.

CHECK 제약조건으로 인해 UPDATE가 실패할 수 있다.

#### 예제

##### 칼럼 데이터 갱신

\<질의\> 이름이 Davenport인 직원의 월급을 갱신하라.

iSQL\> UPDATE employees

SET salary = 2500

WHERE e_lastname = 'Davenport';

1 row updated.

\<질의\> 전 직원의 월급을 7% 인상하라.

iSQL\> UPDATE employees

SET salary = salary \* 1.07;

20 rows updated.

##### WHERE 절에 부질의를 사용해서 데이터 갱신

\<질의\> MYLEE 직원이 받은 주문들의 수량을 50개씩 빼라.

iSQL\> UPDATE orders

SET qty = qty - 50

WHERE eno IN(

SELECT eno

FROM employees

WHERE e_lastname ='Hammond');

9 rows updated.

##### 파티션드 테이블의 데이터 갱신

iSQL\> UPDATE T1 PARTITION(P1) SET I1 = 200;

##### SET 절에 부질의를 갖는 데이터 갱신

\<질의\> 다음 예제는 두개의 중첩된 SELECT 부질의를 갖는 UPDATE 문의 구조를
보여준다.

iSQL\> CREATE TABLE bonuses

(eno INTEGER, bonus NUMBER(10, 2) DEFAULT 100, commission NUMBER(10, 2) DEFAULT
50);

Create success.

iSQL\> INSERT INTO bonuses(eno)

(SELECT e.eno FROM employees e, orders o

WHERE e.eno = o.eno

GROUP BY e.eno);

3 rows inserted.

iSQL\> SELECT \* FROM bonuses;

BONUSES.ENO BONUSES.BONUS BONUSES.COMMISSION

\------------------------------------------------

12 100 50

19 100 50

20 100 50

3 rows selected.

iSQL\> UPDATE bonuses

SET eno = eno + 100, (bonus, commission) =

(SELECT 1.1 \* AVG(bonus), 1.5 \* AVG(commission) FROM bonuses)

WHERE eno IN

(SELECT eno

FROM orders

WHERE qty \>= 10000);

1 row updated.

iSQL\> SELECT \* FROM bonuses;

BONUSES.ENO BONUSES.BONUS BONUSES.COMMISSION

\------------------------------------------------

12 100 50

20 100 50

119 110 75

3 rows selected.

Note: WHERE 절의 부질의 결과가 한 건도 없으면 어떠한 레코드도 영향을 받지
않으나, SET 절의 부질의 결과가 한 건도 없으면 해당 칼럼은 널값으로 갱신될
것이다.

iSQL\> UPDATE orders

SET qty = qty - 50

WHERE eno IN(

SELECT eno

FROM employees

WHERE e_lastname ='Frederick');

No rows updated.

iSQL\> UPDATE employees

SET dno =

(SELECT dno

FROM departments

WHERE dep_location = 'Timbuktu');

20 rows updated.

iSQL\> SELECT e_lastname, dno

FROM employees

WHERE eno = 12;

E_LASTNAME DNO

\-------------------------------

Hammond

1 row selected.

\<질의\> 다음 예제는 UPDATE질의문의 SET절에 DEFAULT를 칼럼에 할당한 후에
질의문을 수행한다.

iSQL\> CREATE TABLE EMPLOYEES (

ENO INTEGER PRIMARY KEY,

E_LASTNAME CHAR(20) NOT NULL,

E_FIRSTNAME CHAR(20) NOT NULL,

EMP_JOB VARCHAR(15),

EMP_TEL CHAR(15),

DNO SMALLINT,

SALARY NUMBER(10,2) DEFAULT 0,

SEX CHAR(1),

BIRTH CHAR(6),

JOIN_DATE DATE,

STATUS CHAR(1) DEFAULT 'H' );

Create success.

iSQL\> SELECT E_FIRSTNAME, SALARY, EMP_JOB FROM EMPLOYEES WHERE EMP_JOB =
'manager' ;

E_FIRSTNAME SALARY EMP_JOB

\-------------------------------------------------------

Gottlieb 500 manager

Xiong manager

Wei-Wei 2300 manager

3 rows selected.

**iSQL\> UPDATE EMPLOYEES SET SALARY=DEFAULT WHERE EMP_JOB = 'manager';**

**3 rows updated.**

**iSQL\> SELECT E_FIRSTNAME, SALARY, EMP_JOB FROM EMPLOYEES WHERE EMP_JOB =
'manager';**

E_FIRSTNAME SALARY EMP_JOB

\-------------------------------------------------------

Gottlieb 0 manager

Xiong 0 manager

Wei-Wei 0 manager

3 rows selected.

##### Returing 절을 사용한 갱신

\<질의\> 다음 예제는 갱신된 행의 값을 출력 바인드 변수 :v1, :v2로 반환한다.

iSQL\> create table employees ( eno integer, ename varchar(20));

Create success.

iSQL\> var v1 output integer;

iSQL\> var v2 output varchar(30);

iSQL\> insert into employees values (1, 'jake');

iSQL\> insert into employees values (2, 'nikita');

iSQL\> insert into employees values (3, 'dana');

iSQL\> prepare update employees set ename='rachel' where eno=3 return eno, ename
into :v1, :v2;

1 row updated.

iSQL\> print var

[ HOST VARIABLE ]

\-------------------------------------------------------

NAME TYPE VALUE

\-------------------------------------------------------

V1 INTEGER 3

V2 VARCHAR(30) rachel

##### 조인 뷰의 데이터 갱신

\<질의\> employees와 departments 테이블의 조인 뷰를 생성한 후, 칼럼 salary를
갱신한다.

iSQL\> CREATE VIEW simple_emp AS

SELECT e.eno, e.e_lastname, e.salary, d.dname

FROM employees e, departments d

WHERE e.dno = d.dno;

Create success.

iSQL\> select \* from simple_emp;

ENO E_LASTNAME SALARY DNAME

\-----------------------------------------------------------------------------------

3 Kobain 2000 RESEARCH DEVELOPMENT DEPT 1

16 Chen 2300 RESEARCH DEVELOPMENT DEPT 1

6 Momoi 1700 RESEARCH DEVELOPMENT DEPT 2

13 Jones 980 RESEARCH DEVELOPMENT DEPT 2

10 Bae 4000 SOLUTION DEVELOPMENT DEPT

11 Liu 2750 SOLUTION DEVELOPMENT DEPT

14 Miura 2003 SOLUTION DEVELOPMENT DEPT

15 Davenport 1000 SOLUTION DEVELOPMENT DEPT

17 Fubuki 1400 QUALITY ASSURANCE DEPT

4 Foster 1800 CUSTOMERS SUPPORT DEPT

1 Moon PRESALES DEPT

5 Ghorbani 2500 PRESALES DEPT

8 Wang MARKETING DEPT

9 Diaz 1200 MARKETING DEPT

18 Huxley 1900 MARKETING DEPT

7 Fleischer 500 BUSINESS DEPT

12 Hammond 1890 BUSINESS DEPT

19 Marquez 1800 BUSINESS DEPT

20 Blake BUSINESS DEPT

19 rows selected.

iSQL\> UPDATE simple_emp SET salary=3000 WHERE dname='RESEARCH DEVELOPMENT DEPT
1';

2 rows updated.

### MOVE 

#### 구문

move ::=

[hints ::=](#hints_diagram), [where_clause ::=](#where_clause), [limit_clause
::=](#limit_clause)

column_commalist ::=

expression_commalist ::=

#### 전제 조건

테이블의 레코드를 이동(MOVE)하기 위해서는 테이블에서 레코드를 삭제할 수 있는
권한과 테이블에 레코드를 삽입할 수 있는 권한이 있어야 한다. 데이터 이동은 삽입과
삭제로 수행되기 때문이다.

INTO 절에 명시된 테이블에 레코드를 삽입하기 위해서는 SYS 사용자이거나 테이블의
소유자이거나 INSERT ANY TABLE 시스템 권한을 가진 사용자, 또는 그 테이블에 대한
INSERT 객체 권한을 가진 사용자이어야 한다.

FROM 절에 명시된 테이블에서 레코드를 삭제하기 위해서는 SYS 사용자이거나 테이블의
소유자이거나 DELETE ANY TABLE 시스템 권한을 가진 사용자, 또는 그 테이블에 대한
DELETE 객체 권한을 가진 사용자이어야 한다.

#### 설명

한 테이블에서 조건을 만족하는 레코드를 찾아 다른 테이블로 이동하는 구문이다.
또한 특정 파티션에 있는 데이터도 이동이 가능하다.

hints

FROM절에 대한 힌트를 제공한다. 이는 SELECT구문에서 사용하는 힌트와 동일하다.

source_tbl_name, target_tbl_name

데이터 이동에 관련된 테이블(원본 테이블과 대상 테이블)을 명시한다. 여기에는 뷰나
메타 테이블이 올 수 없다.

column_commalist

대상 테이블에 속하는 실제 칼럼들의 리스트이다.

expression_commalist

쉼표로 구분된 표현식들의 리스트이다. 각 표현식은 FROM 테이블에 속한 칼럼, 상수,
또는 표현식일 수 있다.

where_clause

SELECT 구문의 WHERE 절과 구조가 동일하다.

limit_clause

SELECT구문의 LIMIT 절과 구조가 동일하다.

#### 주의 사항

동일한 테이블간의 데이터 이동은 불가능하다.

파티션을 지정할 경우 해당 파티션에 맞지 않는 값은 입력될 수 없다.

CHECK 제약조건으로 인해 MOVE가 실패할 수 있다.

#### 예제

\<질의\> t2테이블의 i1, i2 칼럼으로부터 t2.i2=4조건을 만족하는 모든 레코드를 t1
테이블의 i1, i2 칼럼에 삽입하고 t2 테이블에서 삭제한다.

iSQL\> MOVE INTO T1(I1, I2) FROM T2(I1, I2) WHERE T2.I2 = 4;

\<질의\> t2테이블의 i1, i2, i3 칼럼으로 이루어진 레코드를 t1 테이블에 삽입하고
t2테이블에서 삭제한다. (테이블t1에는 t2의 i1, i2, i3 칼럼에 대응되는 칼럼이
있어야 하며 칼럼 개수가 서로 동일해야 한다.)

iSQL\> MOVE INTO T1 FROM T2(I1, I2, I3);

### MERGE

#### 구문

merge ::=

merge_operation_spec ::=

matched_update_clause ::=

not_matched_insert_clause::=

no_rows_insert_clause ::=

#### 전제 조건

MERGE 구문을 사용하기 위해서 사용자는 대상 테이블에 대한 INSERT 및 UPDATE 객체
권한과 원본 테이블에 대한 SELECT 객체 권한을 가져야 한다.

#### 설명

MERGE 구문은 원본 테이블에서 데이터를 조회(SELECT)하여 대상 테이블에
갱신(UPDATE) 또는 삽입(INSERT)하기 위한 구문이다. INTO 절에 명시한 테이블이 대상
테이블이며, USING 절에 명시한 테이블 또는 뷰가 원본 테이블이다. ON 절에는 대상
테이블에 갱신 또는 삽입할 것인지를 결정할 조건을 명시할 수 있다.

INSERST, UPDATE 등의 DML 구문이 여러 번 수행되어야 하는 것을 하나의 MERGE
구문으로 대체할 수 있다.

hints

여기에 명시한 힌트는 적용 가능한 경우 INSERT, UPDATE 작업에 적용될 것이다.

고려 사항:

-   뷰는 대상 테이블로 사용할 수 없다.

-   힌트는 MERGE 키워드 다음에만 올 수 있다.

-   ON 절에 복수의 조건들이 있을 때, 동일한 행에 대하여 각 조건마다 여러 번
    일치할 때에는 해당 행이 반복하여 갱신 또는 삭제될 수 있다.

INTO 절

갱신 또는 삽입할 대상 테이블을 지정하는 절이다. INTO 절에는 뷰는 올 수 없고
테이블만 올 수 있다.

USING 절

원본 데이터를 가져올 테이블 또는 뷰를 지정하는 절이다.

ON 절

ON 절에는 MERGE 작업으로 갱신 또는 삽입할 조건들이 명시된다. 조건 뒤에는 조건
만족 여부에 따라 수행되어야 할 merge 작업이 지정된다. 아래의 세 절을 사용해서
수행될 merge 작업을 지정할 수 있으며, 각 절은 최대 한 번씩만 명시할 수 있고,
순서는 상관 없다.

matched_update_clause

이 절은 대상 테이블에서 갱신될 칼럼 값을 명시한다. ON 절의 조건을 만족하는 행이
원본과 대상 테이블에 있을 경우, 이 절의 갱신이 수행된다.

제약 사항:

-   ON 조건 절에서 참조되는 칼럼은 갱신이 불가능하다.

not_matched_insert_clause

이 절은 ON 절의 조건을 만족하는 행이 대상 테이블에 없는 경우, 대상 테이블의
칼럼에 삽입할 값을 명시한다. INSERT 키워드 다음에 칼럼 리스트를 생략하려면,
VALUES 절에 오는 값의 개수는 대상 테이블의 칼럼 수와 일치해야 한다.

이 절은 단독으로 또는 *merge_update_specification*과 함께 명시할 수 있으며, 둘
모두 명시하는 경우에 순서는 상관 없다.

no_rows_insert_clause

이 절은 ON 절의 조건을 만족하는 행이 원본 테이블에 없는 경우, 대상 테이블의
칼럼에 삽입할 값을 명시한다. INSERT 키워드 다음에 칼럼 리스트를 생략하려면,
VALUES 절에 오는 값의 개수는 대상 테이블의 칼럼 수와 일치해야 한다.

#### 예제

\<질의\>test_merge 테이블에 존재하는 empno의 경우 USING 절에 명시한 값으로
갱신되고, 존재하지 않는 경우에는 삽입되는 것을 보여준다.

CREATE TABLE test_merge (empno int, lastname CHAR(20));

INSERT INTO test_merge values(1, 'KIM');

INSERT INTO test_merge values(2, 'LEE');

INSERT INTO test_merge values(5, 'PARK');

INSERT INTO test_merge values(4, 'CHOI');

INSERT INTO test_merge values(7, 'YUN');

iSQL\> SELECT \* FROM test_merge;

EMPNO LASTNAME

\-------------------------------------

1 KIM

2 LEE

5 PARK

4 CHOI

7 YUN

5 rows selected.

iSQL\> MERGE INTO test_merge old_t

USING

(

SELECT 1 empno, 'KANG' lastname FROM dual UNION ALL

SELECT 7 empno, 'SON' lastname FROM dual UNION ALL

SELECT 9 empno, 'CHEON' lastname FROM dual

) new_t

ON old_t.empno = new_t.empno

WHEN MATCHED THEN

UPDATE SET old_t.lastname = new_t.lastname

WHEN NOT MATCHED THEN

INSERT (old_t.empno, old_t.lastname) VALUES(new_t.empno, new_t.lastname);

3 rows merged.

iSQL\> SELECT \* FROM test_merge;

EMPNO LASTNAME

\-------------------------------------

2 LEE

5 PARK

4 CHOI

1 KANG

7 SON

9 CHEON

6 rows selected.

### ENQUEUE 

#### 구문

enqueue ::=

values_clause ::=

#### 설명

큐에 메시지를 삽입하는 구문이다. ENQUEUE 구문은 INSERT 구문과 유사한 구조를
가지는데 INTO 절 이후에 반드시 하나 이상의 큐 칼럼 명을 명시해야 한다.

일반적인 경우 사용자는 자신이 저장할 메시지만 지정하여 메시지를 입력하는데,
메시지를 구분하거나 분류하여 차별화 할 필요가 있을 때에는 Correlation ID를
명시적으로 지정하여 입력할 수 있다.

#### 예제

\<질의\> “This is a message”라는 메시지를 Q1메시지 큐에 입력하라.

ENQUEUE INTO Q1(message) VALUES ('This is a message');

\<질의\> “This is a message”라는 메시지를 237이라는 Correlation ID로 Q1메시지
큐에 입력하라.

ENQUEUE INTO Q1(message,corrid) VALUES ('This is a message', 237);

### DEQUEUE 

#### 구문

dequeue ::=

![](media/SQL/1f7654cf99a53cff396c356f3256b82f.png)

fifo_option ::=

#### 설명

DEQUEUE 구문은 *where_clause* 절의 조건에 맞는 메시지를 얻어 오고 해당 메시지를
큐에서 삭제한다.

fifo_option

FIFO 옵션이 설정되어 있거나 아무 옵션도 설정하지 않은 경우에는 조건에 맞는
메시지 중 가장 오래된 메시지를 얻어 오고, LIFO 옵션이 설정된 경우에는 가장
최신의 메시지를 얻어 온다.

WAIT integer

DEQUEUE 문은 큐가 비어있을 경우에 메시지가 들어올 때까지 대기한다. WAIT절에
명시한 시간만큼 대기하며, 시간 단위는 second(초), millisecond(msec, 1/1000초),
microsecond(μsec, 1/1000000초)이며 표기하지 않으면 초 단위가 적용된다. 대기
시간이 설정되지 않은 경우, DEQUEUE 문은 무한정 대기할 것이다.

#### 주의사항

DEQUEUE 구문의 사용시에 다음과 같은 점에 주의해야 한다.

-   *queue_column_list*에는 큐 테이블 내의 칼럼명만 지정 가능하다.

-   DEQUEUE문은 SELECT 구문의 일부 특징을 가지고 있지만 DEQUEUE문의 FROM 절에는
    단 하나의 큐 테이블 이름만 지정이 가능하다. 두개 이상의 큐 테이블 이름이
    오면 에러가 발생한다.

-   DEQUEUE구문의 WHERE 절에는 부질의(Subquey)가 올 수 없다.

#### 예제

\<질의\> 메시지 큐 Q1에서 Correlation ID가 237인 메시지들을 모두 읽어라.

DEQUEUE MESSAGE, CORRID FROM Q1 WHERE CORRID=237;

5.데이터 제어어
-------------

이장에서는 사용자 세션 제어와 트랜잭션을 제어하는 SQL문에 대해서 설명한다.

### ALTER REPLICATION 

#### 구문

**alter_replication_dcl ::=**

![](media/SQL/b5f7242764ac5056238e1a91d5783ddb.png)

#### 설명

CREATE REPLICATION 구문으로 이중화 생성 후 이중화의 동작을 제어하는 구문이다.
이중화에 관한 자세한 내용은 *Replication Manual* 을 참고한다.

STOP

이중화를 중지한다.

FLUSH

이 구문이 실행된 세션은 이중화 송신 쓰레드에 의해서 현재 로그(FLUSH구문이 실행된
시점의 로그)까지 변경 내용이 상대방 서버에 전송되도록 *wait_time* 초 만큼
기다린다.

만약 ALL옵션이 함께 사용되면, 구문이 실행된 세션은 현재 로그가 아닌 가장 최근
로그까지의 변경 내용이 상대방 서버에 전송되도록 기다린다.

#### 예제

##### 이름이 rep1인 이중화 객체의 이중화를 중지하라.

\<질의\> 이중화를 중지하라.

iSQL\> ALTER REPLICATION rep1 STOP;

Alter success.

### ALTER SESSION 

#### 구문

alter_session::=

[set_transaction_clause::=](#set_transaction)

alter_session_set_clause::=

replication_mode_set_clause::=

dblink_session_close_clause::=

#### 설명

현재 세션(Session)의 속성을 변경하는 구문이다.

alter_session_set_clause

alter_session_set_clause 절의 property_name과 property\_ value에 관한 자세한
내용은 Altibase 매뉴얼 중 *General Reference*의 Altibase 프로퍼티 장을 참조한다.

replication_mode_set_clause

*replication*\_*mode_set_clause*는 현재 세션에서 수행하는 트랜잭션을 위한 이중화
모드 속성을 설정하는 절이다.

DEFAULT를 명시하면 이중화는 이중화 객체 생성시 기본모드로 채택된 모드로 동작할
것이다. 그러나 NONE을 명시하면 세션에서 수행되는 모든 DDL, DML, DCL 문이 이중화
대상에서 제외된다.

이중화 모드에 대한 보다 자세한 내용은 *Replication Manual*을 참조한다.

dblink_session \_close_clause

사용자가 서버에 접속하면 서버에는 세션이 생성된다. 이 세션에서 데이터베이스
링크를 사용하면, 데이터베이스 링크 작업을 위한 데이터베이스 링크 세션이
사용자에게 할당된 세션내에 생성된다. 그리고 이 사용자 세션이 종료될 때,
데이터베이스 링크 세션도 같이 종료된다. 그런데 데이터베이스 링크 작업을 한번
수행한 후, 이 사용자 세션을 종료하지 않은 채로 계속 유지한다면, 불필요한
데이터베이스 링크 세션이 남아있게 된다.

이 경우 이 절을 사용하여 데이터베이스 링크 세션을 정리할 수 있다.

set_transaction_clause

현재 세션에서 수행되는 트랜잭션에 read only, read/write**오류! 책갈피가 정의되어
있지 않습니다.** 또는 고립화 수준(isolation level)을 설정할 수 있다. 자세한
내용은 이 매뉴얼의 [SET TRANSACTION](#set_transaction) 구문을 참조한다.

#### 예제

\<질의\> 현재 세션은 그냥두고 데이터베이스 링크 세션만 종료한다.

iSQL\> ALTER SESSION CLOSE DATABASE LINK ALL;

### ALTER SYSTEM 

#### 구문

alter_system ::=

![](media/SQL/06225f64896e240962da9ad1a2374037.png)

alter_system_set_clause ::=

#### 설명

Altibase의 시스템 프로퍼티를 변경하는 구문이다. SYS 사용자 또는 ALTER SYSTEM
권한을 가진 사용자만이 ALTER SYSTEM 문의 모든 기능을 수행할 수 있다.

CHECKPOINT

체크포인트를 수행하는 옵션이다.

MEMORY COMPACT

메모리 콤팩션을 수행하는 구문이다. 이 구문은 IBM AIX플랫폼에서만 동작한다.

START/STOP FLUSHER integer

Altibase 플러셔를 구동하거나 정지시키는 구문이다. 정수값의 플러셔 ID는
V\$FLUSHER 성능 뷰를 통해서 조회할 수 있다.

ARCHIVE LOG START/STOP

START를 실행하면 아카이브로그 쓰레드가 시작되고, STOP하면 종료된다. Altibase가
아카이브로그 모드로 운영중일때만 이 구문을 실행할 수 있다.

Altibase가 아카이브로그 모드로 운영중인지 여부는 V\$LOG 또는 V\$ARCHIVE 성능
뷰에서 확인이 가능하다. 아카이브로그 모드에 대한 자세한 내용은 *Administrator’s
Manual*의 10장 백업 및 복구를 참고한다.

SWITCH LOGFILE

로그파일을 강제로 아카이브하는 구문이다. 현재 로그파일이 꽉 차지 않았더라도, 이
구문을 실행하면 Altibase는 사용중이던 로그파일을 닫고 다음 로그파일에 로깅을
계속한다.

이 구문은 sysdba모드로만 수행할 수 있다.

SET alter_system_set_clause

Altibase 프로퍼티 값을 변경하는 구문이다. 프로퍼티에 대한 자세한 내용은 *General
Reference*의 Altibase 프로퍼티를 참조한다.

FLUSH BUFFER_POOL

버퍼에 있는 모든 페이지를 디스크로 내리고, 버퍼를 비운다.

이 구문은 sysdba모드로만 수행할 수 있다. 사용할 때는 반드시 주의를 기울여야
한다. 이 구문을 수행할 경우 버퍼에 있는 모든 페이지가 삭제되기 때문에, 다음에
수행되는 질의문은 접근하는 모든 페이지에 대해서 버퍼 미스(Buffer Miss, 버퍼에서
레코드를 찾는 데 실패하는 것을 말함)를 발생시킨다.

COMPACT SQL_PLAN_CACHE

SQL Plan Cache에서 사용되지 않는 실행 계획을 삭제한다.

RESET SQL_PLAN_CACHE

SQL Plan Cache에 사용되지 않는 실행 계획을 삭제하고 Plan Cache 관련 통계 정보를
초기화한다.

START \| STOP \| RELOAD AUDIT

감사(Auditing)를 시작 또는 중지하거나, 감사 조건을 재적용하는 구문이다.

RELOAD ACCESS LIST

IP 패킷의 접근을 허용하거나 차단하는 목록을 갱신한다. sysdba 관리자 모드로만 이
구문을 수행할 수 있다. ACCESS_LIST_FILE 프로퍼티에 설정된 파일의 목록으로 ACCESS
LIST를 구성한다. ACCESS LIST에 대한 자세한 내용은 ACCESS_LIST 프로퍼티를
참조한다.

#### 예제

\<질의\> 플러셔 1번을 중지시킨다.

iSQL\> ALTER SYSTEM STOP FLUSHER 1;

\<질의\> 아카이브로그 모드일 경우 아카이브 로그 쓰레드를 시작시킨다.

iSQL\> ALTER SYSTEM ARCHIVE LOG START;

### AUDIT

#### 구문

audit ::=

audit_operation_clause ::=

by_clause ::=

audit_object_clause ::=

ddl_clause ::=

#### 전제 조건

SYS 사용자만이 이 구문으로 감사 조건을 설정할 수 있다.

#### 설명

Altibase 서버 내에서 실행되고 있는 특정 구문 또는 모든 구문을 실시간으로
추적하고, 로그를 남기는 것을 감사(Audit)라고 한다. 이 구문을 사용해서 감사
조건을 설정할 수 있다.

audit_operation_clause

이 절은 Altibase 서버에서 특정한 SQL 구문이 수행되는 것을 감사하도록 지정한다.

이 절의 sql_statement_type에는 감사 대상 작업을 지정한다. 콤마(,)로 연결해서
여러 개를 명시할 수도 있다. 지정 가능한 감사 작업은 다음과 같다.

-   SELECT

-   INSERT

-   UPDATE

-   DELETE

-   MOVE

-   MERGE

-   ENQUEUE

-   DEQUEUE

-   LOCK

-   EXEC or EXECUTE

-   COMMIT

-   ROLLBACK

-   SAVEPOINT

-   CONNECT

-   DISCONNECT

-   ALTER SESSION

-   ALTER SYSTEM

ALL은 위에 나열한 모든 구문에 대해 감사할 것을 지정한다.

by_clause

특정 사용자가 실행하는 구문을 감사할 것을 지정한다.

audit_object_clause

이 절은 Altibase 서버에서 특정 객체에 대해 특정한 작업이 수행되는 것을
감사하도록 지정한다.

이 절에는 감사 대상 작업을 콤마(,)로 연결해서 명시할 수 있다. 아래는 감사 대상이
될 수 있는 작업 별로 지정 가능한 객체의 종류와, 각 경우에 감사 내역은 무엇인지를
나타낸 표이다.

| 작업         | 객체 종류 | 감사 내역                               |
|--------------|-----------|-----------------------------------------|
| SELECT       | TABLE     | 대상 테이블 객체에 수행되는 SELECT 구문 |
| INSERT       | TABLE     | 대상 테이블 객체에 수행되는 INSERT 구문 |
| UPDATE       | TABLE     | 대상 테이블 객체에 수행되는 UPDATE 구문 |
| DELETE       | TABLE     | 대상 테이블 객체에 수행되는 DELETE 구문 |
| MOVE         | TABLE     | 대상 테이블 객체에 수행되는 MOVE 구문   |
| MERGE        | TABLE     | 대상 테이블 객체에 수행되는 MERGE 구문  |
| ENQUEUE      | QUEUE     | 대상 큐 객체에 수행되는 ENQUEUE 구문    |
| DEQUEUE      | QUEUE     | 대상 큐 객체에 수행되는 DEQUEUE 구문    |
| LOCK         | TABLE     | 대상 테이블 객체에 수행되는 LOCK 구문   |
| EXEC/EXECUTE | PROCEDURE | 대상 프로시저 객체를 실행하는 구문      |

ALL은 객체 유형에 대해서 수행 가능한 모든 SQL 구문을 감사할 것을 지정한다. 단,
위의 표에 나열한 구문에 한해서이다.

object_name

감사 대상이 되는 객체 이름을 명시한다. 지정할 수 있는 객체의 종류는 테이블, 뷰,
큐, 시퀀스, 저장 프로시저 및 저장 함수이다.

ddl_clause

이 절은 Altibase 서버에서 DDL 구문이 수행되는 것을 감사하도록 지정한다.

BY ACCESS \| SESSION

BY ACCESS를 지정하면 조건에 부합하는 구문 또는 작업에 대해 각각 하나의 감사
로그가 기록된다. 예를 들어 BY ACCESS를 지정하여 감사를 진행하면 한 세션에서
동일한 SQL 구문이 10회 실행된 경우 감사 로그도 10개가 기록된다.

BY SESSION을 지정하면 동일한 세션에서 동일한 SQL 구문이 실행될 때에는 하나의
감사 로그만 기록된다. 즉 BY SESSION을 지정하여 감사를 진행하면 한 세션에서
동일한 SQL 구문이 실행될 때 중복해서 로그를 남기지 않는다.

둘 중 하나도 지정하지 않으면 BY SESSION이 디폴트이다.

감사 대상이 CONNECT, DISCONNECT, DDL 경우에는 BY ACCESS\|SESSION을 지원하지
않는다.

WHENEVER [NOT] SUCCESSFUL

WHENEVER SUCCESSFUL을 지정하면 성공하는 SQL구문과 작업만 감사한다.

WHENEVER NOT SUCCESSFUL을 지정하면 실패하는 SQL구문과 작업만 감사한다.

이 절을 생략하면 Altibase는 성공이나 실패에 상관없이 감사를 수행한다.

'BY SESSION WHENEVER SUCCESSFUL'로 지정한 경우, 한 세션에서 수행된 동일한 SQL
구문들이 모두 성공적으로 수행되는 경우에만 그 구문에 대한 로그가 기록된다.

'BY SESSION WHENEVER NOT SUCCESSFUL'로 지정한 경우, 한 세션에서 수행되는 동일한
SQL 구문들 중 하나라도 실패할 경우에 그 구문에 대한 로그가 기록된다.

#### 주의 사항

AUDIT 구문으로 감사 조건을 설정하여도, 서버의 감사 작업에 새로운 조건들이 바로
적용되는 것은 아니다. 운영 중인 서버에 새로운 감사 조건들이 적용되기 위해서는
아래의 구문을 사용해서 감사를 재시작하거나 감사 조건들을 RELOAD해야 한다.

>   ALTER SYSTEM STOP AUDIT;

>   ALTER SYSTEM START AUDIT;

>   ALTER SYSTEM RELOAD AUDIT;

#### 예제

\<질의1\> 사용자 user1의 friends 테이블에 대한 INSERT, UPDATE 또는 DELETE문 수행
중 실패한 경우에 대한 정보를 모두 기록하라.

iSQL\> AUDIT insert, update, delete ON user1.friends BY ACCESS WHENEVER NOT
SUCCESSFUL;

\<질의2\> 사용자 user1의 friends 테이블에 대한 DDL문 수행들이 세션에서 모두
성공한 경우에 로그를 기록하라.

iSQL\> AUDIT all ON user1.friends BY SESSION WHENEVER SUCCESSFUL;

\<질의3\> Altibase 서버에 대해 수행되는 모든 CONNECT, DISCONNECT 구문의 실패
정보를 기록하라.

iSQL\> AUDIT connect, disconnect WHENEVER NOT SUCCESSFUL;

Audit success

\<질의4\> Altibase 서버 내에서 수행되는 모든 INSERT 구문에 대한 정보를 세션
단위로 기록하라.

iSQL\> AUDIT insert;

Audit success.

\<질의5\> 사용자 user1이 수행하는 모든 DDL 구문에 대한 로그를 기록하라.

iSQL\> AUDIT DDL BY user1;

Audit success.

### COMMIT 

#### 구문

commit::=

![](media/SQL/ce2daf567e6435f7b5ff96bed4c4021b.png)

#### 설명

현재의 트랜잭션을 데이터베이스에 명시적으로 커밋하는 구문이다.

AUTOCOMMIT 모드가 FALSE일때 사용할 수 있다.

WORK

WORK 키워드는 표준 SQL을 준수하도록 한다.

FORCE global_tx_id

XA환경에서 트랜잭션이 in-doubt 상태가 될 경우에 이를 강제로 커밋하는 구문이다.

global_tx_id는 글로벌 트랜잭션의 포맷(format) 아이디, 글로벌 트랜잭션(global
transaction) 아이디, 브랜치 수식자(branch qualifier)를 문자열로 나타낸 것이다.

#### 주의 사항

AUTOCOMMIT 모드 시에 이 문장을 수행할 수 없다.

#### 예제

다음 구문은 트랜잭션이 이전에 수행한 모든 명령들을 데이터베이스에 반영한다..

iSQL\> COMMIT;

Commit success.

### DELAUDIT

#### 구문

delaudit ::=

delaudit_user_clause ::=

delaudit_object_clause ::=

#### 전제 조건

SYS 사용자만이 이 구문으로 감사 조건을 삭제할 수 있다.

#### 설명

Altibase 서버 내에서 감사를 하기 위해 설정한 감사 조건을 삭제하는 구문이다.

delaudit_user_clause

AUDIT ... BY *user_name* 구문으로 설정한 구문 감사와 DDL 감사 조건들 중 지정한
사용자 이름과 일치하는 것을 삭제한다.

ALL

BY *user_name*절 없이 설정한 구문 감사 조건과 DDL 감사 조건을 일괄적으로
삭제한다. 객체 감사 조건은 삭제되지 않는다.

delaudit_object_clause

특정 객체에 대해 설정된 감사 조건을 삭제한다.

#### 주의 사항

DELAUDIT 구문이 실행되면, SYS_AUDIT_OPTS_에서 감사 조건들이 삭제된다.

감사가 이미 시작되어 있는 경우에는 이 구문을 실행할 수 없다. 만약 감사가
시작되어 있는 상태에서 감사 조건을 삭제할 경우 에러가 발생하며, ALTER SYSTEM
STOP AUDIT으로 감사를 종료 후 삭제한다.

#### 예제

\<질의1\> 사용자 user1에 대한 감사 조건을 삭제한다. 구문 실행 후에,
SYS_AUDIT_OPTS_에서 감사 조건이 삭제된 것을 확인할 수 있다.

iSQL\> DELAUDIT by user1;

Audit success.

iSQL\> SELECT \* from SYSTEM_.SYS_AUDIT_OPTS_;

No rows selected.

\<질의 2\> 구문 감사가 시작된 후에, DELAUDIT을 실행하면 에러가 발생한다. 감사를
종료 후 삭제할 수 있다.

iSQL\> alter system start audit;

Alter success.

iSQL\> delaudit by user1;

[ERR-313B2 : Audit has already started.]

iSQL\> alter system stop audit;

Alter success.

iSQL\> delaudit by user1;

Audit success.

### NOAUDIT

#### 구문

noaudit ::=

audit_operation_clause ::=

by_clause ::=

audit_object_clause ::=

ddl_clause ::=

#### 전제 조건

SYS 사용자만이 이 구문으로 감사 조건을 해제할 수 있다.

#### 설명

NOAUDIT 구문은 이전에 AUDIT 구문으로 설정한 감사 조건을 해제하기 위해 사용된다.

audit_operation_clause

이 절은 특정 SQL 구문에 대한 감사를 중지하기 위해 사용된다.

sql_statement_type에는 중지할 감사 작업을 지정한다. 지정 가능한 감사 작업에
대해서는 AUDIT 구문의 설명을 참고하라.

ALL은 이전에 AUDIT ALL 구문으로 설정한 모든 구문에 대한 감사를 중지하기 위해
사용된다.

audit_object_clause

이 절은 특정 객체에 대한 감사 조건을 해제하기 위해 사용된다.

sql_operation에는 ON 절에 명시한 객체에 대해 감사를 중지할 SQL 작업을 지정하면
된다. 지정 가능한 SQL 작업에 대해서는 AUDIT 구문의 설명을 참고하라.

ALL은 객체 유형에 대해서 수행 가능한 모든 SQL 구문을 지정하는 것과 동일한 역할을
한다.

ddl_clause

이 절은 DDL 구문에 대한 감사를 중지하도록 지정한다.

WHENEVER [NOT] SUCCESSFUL

WHENEVER SUCCESSFUL은 SQL 구문과 객체에 대한 작업이 성공하는 것에 대한 감사를
중지할 것을 지정한다.

WHENEVER NOT SUCCESSFUL은 SQL 구문과 객체에 대한 작업이 실패하는 것에 대한
감사를 중지할 것을 지정한다.

이 절을 생략하면 성공 또는 실패 여부에 상관없이 지정한 구문 또는 객체에 대한
작업을 감사하는 것을 중지할 것을 지정한다.

#### 주의 사항

NOAUDIT 구문으로 어떤 감사 조건을 해제하여도, 서버의 감사 작업에 바로 적용되는
것은 아니다. 운영 중인 서버에 감사 조건의 해제가 적용되기 위해서는 아래의 구문을
사용해서 감사를 재시작하거나 감사 조건들을 RELOAD해야 한다.

>   ALTER SYSTEM STOP AUDIT;

>   ALTER SYSTEM START AUDIT;

>   ALTER SYSTEM RELOAD AUDIT;

#### 예제

\<질의1\> 테이블 friends에서 SELECT 구문의 성공에 대한 감사를 해제하라.

iSQL\> NOAUDIT select ON friends WHENEVER SUCCESSFUL;

Audit success.

\<질의2\> SELECT 구문에 대한 감사를 해제하라.

iSQL\> NOAUDIT select;

Audit success.

\<질의3\> DDL 문에 대한 감사를 해제하라.

iSQL\> NOAUDIT DDL;

Audit success.

### SAVEPOINT

#### 구문

savepoint::=

#### 설명

저장점을 생성하는 구문이다. 저장점의 생성은 지금까지 실행된 트랜잭션 처리의
결과를 임시로 저장하는 것을 의미한다. 즉, 저장점은 트랜잭션 내에서 롤백할 지점을
명시적으로 지정한 것이다. 저장점은 AUTOCOMMIT 모드가 FALSE 일 때 유효하다.

#### 주의 사항

자동반영(AUTOCOMMIT) 모드일 때 사용할 수 없다.

#### 예제

iSQL\> AUTOCOMMIT OFF;

Set autocommit off success.

iSQL\> CREATE TABLE savept(num INTEGER);

Create success.

iSQL\> INSERT INTO savept VALUES(1);

1 row inserted.

iSQL\> SAVEPOINT sp1;

Savepoint success.

iSQL\> INSERT INTO savept VALUES(2);

1 row inserted.

iSQL\> SELECT \* FROM savept;

SAVEPT.NUM

\--------------

1

2

2 rows selected.

저장점 sp1 지점까지 트랜잭션을 롤백한다.

iSQL\> ROLLBACK TO SAVEPOINT sp1;

Rollback success.

iSQL\> SELECT \* FROM savept;

SAVEPT.NUM

\--------------

1

1 row selected.

iSQL\> COMMIT;

Commit success.

### ROLLBACK 

#### 구문

rollback ::=

![](media/SQL/60e568043cca326e4368cab5e5f8c46e.png)

#### 설명

ROLLBACK (TO SAVEPOINT)

현재의 트랜잭션을 모두 롤백하거나 (이전에 정의한) 저장점까지 부분 롤백하는
구문이다.

FORCE global_tx_id

XA환경에서 “in-doubt”상태의 트랜잭션을 강제로 롤백하는 구문이다.

global_tx_id는 글로벌 트랜잭션의 포맷(format) 아이디, 글로벌 트랜잭션(global
transaction) 아이디, 브랜치 수식자(branch qualifier)를 문자열로 나타낸 것이다.

#### 주의 사항

이 구문은 AUTOCOMMIT 모드일 때는 사용할 수 없다.

#### 예제

iSQL\> AUTOCOMMIT OFF;

Set autocommit off success.

iSQL\> UPDATE employees SET salary = 2300 WHERE eno = 3;

1 row updated.

iSQL\> SAVEPOINT emp3_sal;

Savepoint success.

iSQL\> DELETE FROM employees WHERE eno = 19;

1 row deleted.

iSQL\> SAVEPOINT emp19_ret;

Savepoint success.

iSQL\> INSERT INTO employees(eno, e_lastname, e_firstname, salary, sex)
VALUES(21, 'Templeton', 'Kimmie', 3000, 'F');

1 row inserted.

iSQL\> SAVEPOINT emp21_join;

Savepoint success.

iSQL\> UPDATE employees SET salary = 2200 WHERE eno=18;

1 row updated.

iSQL\> SELECT eno, e_lastname, e_firstname, salary FROM employees WHERE eno in
(3, 18, 19, 21);

ENO E_LASTNAME E_FIRSTNAME SALARY

\-------------------------------------------------------------------------

3 Kobain Ken 2300

18 Huxley John 2200

21 Templeton Kimmie 3000

3 rows selected.

저장점 emp21_join 지점까지 트랜잭션을 롤백한다.

iSQL\> ROLLBACK TO SAVEPOINT emp21_join;

Rollback success.

iSQL\> SELECT eno, e_lastname, e_firstname, salary FROM employees WHERE eno in
(3, 18, 19, 21);

ENO E_LASTNAME E_FIRSTNAME SALARY

\-------------------------------------------------------------------------

3 Kobain Ken 2300

18 Huxley John 1900

21 Templeton Kimmie 3000

3 rows selected.

저장점 emp19_ret 지점까지 트랜잭션을 롤백한다.

iSQL\> ROLLBACK TO SAVEPOINT emp19_ret;

Rollback success.

iSQL\> SELECT eno, e_lastname, e_firstname, salary FROM employees WHERE eno in
(3, 18, 19, 21);

ENO E_LASTNAME E_FIRSTNAME SALARY

\-------------------------------------------------------------------------

3 Kobain Ken 2300

18 Huxley John 1900

2 rows selected.

첫 번째 UPDATE 문, 첫번째 DELETE문과 마지막 DML문 (두 번째 INSERT문)에 의해
수행된 모든 변경을 커밋한다. 모든 다른 DML 문들의 변경사항은 COMMIT 되기 전에
롤백되어 사라졌다. 또한 저장점 emp21_join은 더 이상 유효하지 않다.

iSQL\> ROLLBACK TO SAVEPOINT emp21_join;

[ERR-11016 : Savepoint not found]

iSQL\> INSERT INTO employees(eno, e_lastname, e_firstname, sex, join_date)
VALUES(22, 'Chow', 'May', 'F', TO_DATE('2011-11-19 00:00:00', 'YYYY-MM-DD
HH:MI:SS'));

1 row inserted.

iSQL\> COMMIT;

Commit success.

iSQL\> SELECT eno, e_lastname, e_firstname, salary FROM employees;

ENO E_LASTNAME E_FIRSTNAME SALARY

\-------------------------------------------------------------------------

1 Moon Chan-seung

2 Davenport Susan 1500

4 Foster Aaron 1800

5 Ghorbani Farhad 2500

6 Momoi Ryu 1700

7 Fleischer Gottlieb 500

8 Wang Xiong

9 Diaz Curtis 1200

10 Bae Elizabeth 4000

11 Liu Zhen 2750

12 Hammond Sandra 1890

13 Jones Mitch 980

14 Miura Yuu 2003

15 Davenport Jason 1000

16 Chen Wei-Wei 2300

17 Fubuki Takahiro 1400

18 Huxley John 1900

20 Blake William

3 Kobain Ken 2300

22 Chow May 0

20 rows selected.

iSQL\> COMMIT;

Commit success.

### SET TRANSACTION 

#### 구문

set_transaction ::=

#### 설명

SET TRANSACTION 구문은 현재 세션에서 수행되는 트랜잭션에 read only, read/write
또는 고립화 수준(isolation level)을 설정할 수 있다.

고립화 수준을 READ COMMITTED 또는 SERIALIZABLE로 설정하면 행 수준 잠금과
다중버전 제어기법의 조합을 통하여 높은 수준의 데이터 일관성, 동시성 그리고
성능을 제공한다.

SET TRANSACTION 구문에 의해 수행된 동작들은 다른 사용자들이나 다른 트랜잭션이
아닌 오로지 현재 트랜잭션에만 영향을 미친다.

다음과 같은 3개의 고립화 수준 중 하나를 설정할 수 있다.

READ COMMITTED

테이블 내의 커밋된 데이터에 대해 읽기를 허용하며, 커밋되지 않은 데이터에
대해서는 이전 버전의 값을 읽도록 동작한다. Altibase의 기본 고립화 수준은 READ
COMMITTED이다.

REPEATABLE READ

트랜잭션이 읽어간 데이터에 대해 그 트랜잭션이 완료될 때까지 잠금을 걸어서, 해당
데이터에 대한 다른 트랜잭션의 변경을 금지한다. 이러한 동작은 반복적으로 그 값을
다시 읽었을 때도 항상 같은 값이 반환될 것을 보장한다. 그러나 잠금이 걸려 있는
상태에서도 읽어간 검색 범위안에 포함되는 새로운 레코드를 다른 트랜잭션이
삽입하는 것은 가능하다. 이러한 레코드는 잠금을 걸고 있는 읽기 트랜잭션에 의한
최초 조회시에는 보이지 않았지만 삽입 이후에는 보일 것이다. 이를 “Phantom
Reads”라고 한다.

SERIALIZABLE

이는 가장 높은 고립화 수준이다. 이는 한번 SELECT하여 가져간 모든 데이터에
공유잠금을 걸뿐만 아니라, 그 검색 범위안에 있는 모든 키 값에 대해서도 잠금을
걸게 된다. 이는 “phantom reads”를 방지하는 효과를 내어 트랜잭션의
독립성(isolation)을 보장한다.

#### 주의 사항

현재 세션이 AUTOCOMMIT 모드일 경우에는 이 구문을 사용할 수 없다.

활성화된 트랜잭션이 있을 경우에는 이 구문을 사용할 수 없다.

#### 예제

iSQL\> AUTOCOMMIT OFF;

Set autocommit off success.

iSQL\> SET TRANSACTION ISOLATION LEVEL READ COMMITTED;

Command execute success.

iSQL\> SET TRANSACTION ISOLATION LEVEL REPEATABLE READ;

Command execute success.

| Transaction A                                                                                                      | Time Point | Transaction B                                                                  |
|--------------------------------------------------------------------------------------------------------------------|------------|--------------------------------------------------------------------------------|
| iSQL\> AUTOCOMMIT OFF; Set autocommit off success.                                                                 |            | iSQL\> AUTOCOMMIT OFF; Set autocommit off success.                             |
| iSQL\> SET TRANSACTION READ ONLY; Command execute success.                                                         | 1          |                                                                                |
| iSQL\> SELECT e_last name FROM employees WHERE eno = 20; E_LASTNAME ------------------------ Blake 1 row selected. | 2          |                                                                                |
|                                                                                                                    | 3          | iSQL\> UPDATE employees SET e_lastname = 'Jung' WHERE eno = 20; 1 row updated. |
| iSQL\> SELECT e_lastname FROM employees WHERE eno = 20; E_LASTNAME ------------------------ Blake 1 row selected.  | 4          |                                                                                |
|                                                                                                                    | 5          | iSQL\> commit; Commit success.                                                 |
| iSQL\> SELECT e_lastname FROM employees WHERE eno = 20; E_LASTNAME ------------------------ Jung 1 row selected.   | 6          |                                                                                |

집합 연산자 
------------

이 장에서는 SQL 질의 실행 결과 집합을 대상으로 연산하는 집합 연산자들에 대해서
설명한다.

### UNION

#### 구문

SELECT *statement1* **UNION** SELECT *statement2*

#### 설명

두 질의문의 결과를 모두 반환하는 연산자이다. 단, 양쪽 질의의 결과에 동일한 값이
있을 경우 한건만 반환된다.

#### 예제

\<질의\> 생일이 1980년 이후인 사원과 100개 미만의 주문량을 받은 사원의
사원번호를 출력하라. 중복된 사원번호는 한번만 출력되게 하라.

iSQL\> SELECT eno

FROM employees

WHERE birth \> '800101'

UNION

SELECT eno

FROM orders

WHERE qty \< 100;

ENO

\--------------

4

7

8

12

13

15

20

7 rows selected.

### UNION ALL

#### 구문

SELECT *statement1* **UNION ALL** SELECT *statement2*

#### 설명

두 질의문의 결과를 모두 반환하는 연산자이다. 양쪽 질의의 결과에 동일한 값이 있을
경우에 중복된 값이 모두 반환된다.

#### 예제

\<질의\> 생일이 1980년 이후인 사원과 100개 미만의 주문량을 받은 사원의
사원번호를 출력하라. 중복된 사원번호도 모두 출력되게 하라.

iSQL\> SELECT eno

FROM employees

WHERE birth \> '800101'

UNION ALL

SELECT eno

FROM orders

WHERE qty \< 100;

ENO

\--------------

4

7

8

12

13

15

12

20

20

9 rows selected.

### INTERSECT

#### 구문

SELECT *statement1* **INTERSECT** SELECT *statement2*

#### 설명

두 질의문의 결과 중 공통된 행을 반환하는 연산자이다.

#### 예제

\<질의\> 한번이라도 주문된 적이 있는 상품을 모두 출력하라.

iSQL\> SELECT gno FROM goods

INTERSECT

SELECT gno FROM orders;

GNO

\--------------

.

.

.

### MINUS

#### 구문

SELECT *statement1* **MINUS** SELECT *statement2*

#### 설명

첫번째 검색 결과에서 두 번째 검색 결과를 제외한 결과를 반환하는 연산자이다.

#### 예제

\<질의\> 한번도 주문된 적이 없는 상품들의 제품번호를 출력하라.

iSQL\> SELECT gno FROM goods

MINUS

SELECT gno FROM orders;

GNO

\--------------

.

.

.

### 연산 순서

연산의 순서 즉, 연산자 우선 순위는 데이터베이스 서버가 수식 내의 연산자들을
처리하는 순서이다. 다수의 연산자를 포함하는 수식이 처리될 때, 높은 우선순위의
연산자가 낮은 우선순위의 연산자보다 먼저 처리된다. 같은 우선순위를 갖는 연산자는
수식 내에서 나열된 순서 즉, 왼쪽에서 오른쪽으로 처리된다.

#### 설명

SQL 연산자의 연산 우선순위를 내림차순으로 다음 표에 보여주고 있다. 수식 내에
괄호를 사용하여 우선순위 규칙보다 우선 적용되게 할수 있다.

| 우선순위 레벨 | 연산자           |
|---------------|------------------|
| 1             | 모든 비교 연산자 |
| 2             | NOT              |
| 3             | AND              |
| 4             | OR               |

#### 예제

\<질의\> 월급이 1850 달러를 넘는 엔지니어의 이름, 직위, 급여와 급여에 상관없이
모든 영업 사원의 이름, 직위, 급여를 출력하라.

iSQL\> SELECT e_firstname, e_lastname, emp_job, salary

FROM employees

WHERE emp_job = 'sales rep'

OR emp_job = 'engineer'

AND salary \>= 1850;

E_FIRSTNAME E_LASTNAME EMP_JOB SALARY

\------------------------------------------------------------------------------

Ken Kobain engineer 2000

Sandra Hammond sales rep 1890

Alvar Marquez sales rep 1800

William Blake sales rep

4 rows selected.

\<질의\> 월급이 1850 달러를 넘는 엔지니어의 이름, 직위, 급여와 월급이 1850
달러를 넘는 영업 사원의 이름, 직위, 급여를 출력하라.

iSQL\> SELECT e_firstname, e_lastname, emp_job, salary

FROM employees

WHERE (emp_job = 'sales rep'

OR emp_job = 'engineer')

AND salary \>= 1850;

E_FIRSTNAME E_LASTNAME EMP_JOB SALARY

\------------------------------------------------------------------------------

Ken Kobain engineer 2000

Sandra Hammond sales rep 1890

2 rows selected.


