# Yearly windowed h-index
```
해당 repository 를 fork 한 뒤, fork 된 repository 에서 과제를 수행해 주세요.
```

## Dataset
- `paper_author.csv` 파일은 다음과 같은 column 으로 이루어져 있습니다.
  - `author_id` - string, 저자의 ID
  - `paper_id` - string, 저자가 작성한 논문의 ID
  - `published_at` - string, 저자가 작성한 논문이 출판된 날짜, **yyyy-MM-dd**
  - `author_sequence` - int, 논문 내 저자의 순서
- `paper_reference.csv` 파일은 다음과 같은 column 으로 이루어져 있습니다
  - `paper_id` - string, 논문의 ID
  - `reference_paper_id` - string, 논문 {`paper_id`} 가 인용한 논문의 ID
- 첫 행은 column 이름으로 이루어져 있습니다.
- 저자의 수는 최소 1명, 최대 8명입니다.
- 피인용논문은 인용한 논문보다 언제나 과거에 출판된 논문입니다.
- `paper_id` 와 `reference_paper_id` 는 항상 다른 값을 가집니다.
- 모든 날짜는 **2010년 1월 1일** 이후의 값을 가집니다.

## h-index
***h-index*** 의 정의는 다음과 같습니다.

>“A scientist has index h if h of his or her Np papers have at least h citations each and the other (Np – h) papers have ≤h citations each.”

***Windowed h-index*** 는 window 의 크기를 정하여 계산하는 방식으로, 기준 년도에서 *n* 년 이내에 작성된 논문만을 이용하여 계산된 h-index 입니다. 표기는 h*n*-index 로 표기하는데, 예를 들어, 만약 2년 내의 출판물로 계산한 경우 h2-index 로 표기합니다.


## Assignments
> **Requirements**
> 
> 모든 답변은 repository 내에 존재하고 있는 `answer<n>.sql` 와 `answer.py` 내에 작성해주세요.
> 
> `SQL`
>
> 모든 답변은 [***sqlite***](https://www.sqlite.org/lang.html) 에서 작동하는 SQL 쿼리로 작성해주세요.
> 
> 주어진 데이터를 이용해 생성된 테이블명은 `paper_author` 와 `paper_reference` 라고 가정합니다.
>
> `Python`
>
> 모든 답변은 [***pandas***](https://pandas.pydata.org/docs/reference/index.html#api) 만을 이용하여 작동하는 python 코드로 작성해주세요.
>
> 각 항목의 답은 `answer.py` 내의 `answer<n>()` 함수 내에 작성해주세요.
>
> `Common requirements`
>
> 모든 날짜는 말일을 기준으로 계산합니다.
>
> 출력값의 column 은 각 문항의 마지막 괄호 안의 이름과 순서, 자료형을 따라주세요.

1. 각 저자의 출판수와 인용수를 구하는 쿼리를 작성하세요. *(author_id\<string>, publication_count\<int>, citation_count\<int>)*
2. 각 저자의 년도*yyyy*별 출판수와 인용수를 구하는 쿼리를 작성하세요. *(author_id\<string>, year\<int>, publication_count\<int>, citation_count\<int>)*
3. 각 저자의 년-월*yyyy-MM*별 출판수와 인용수를 구하는 쿼리를 작성하세요. *(author_id\<string>, yearmonth\<string>, publication_count\<int>, citation_count\<int>)*
4. 각 저자의 h-index 를 구하는 쿼리를 작성하세요. *(author_id\<string>, hindex\<int>)*
5. 각 저자의 h5-index 를 구하는 쿼리를 작성하세요. *(author_id\<string>, h5index\<int>)*
6. 각 저자의 년도*yyyy*별 해당 시점에서의 h-index 를 구하는 쿼리를 작성하세요. *(author_id\<string>, year\<int>, hindex\<int>)*
7. 각 저자의 년도*yyyy*별 해당 시점에서의 h5-index 를 구하는 쿼리를 작성하세요. *(author_id\<string>, year\<int>, h5index\<int>)*
8. 각 저자의 년-월*yyyy-MM*별 해당 시점에서의 h5-index 를 구하는 쿼리를 작성하세요. *(author_id\<string>, yearmonth\<string>, h5index\<int>)*