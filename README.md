# GFM
## Tables
* 테이블은 데이터에서 헤더를 구분하는 delimiter row가 있으며 각행은 파이프(|)로 열을 나눕니다.
* delimiter row는 하이픈(-)만을 사용하며 일반 행과 마찬가지로 파이프(|)로 열을 나눕니다.  
* **주의**: 헤더 행의 셀 수는 delimeter row의 행 수와 같아야합니다. 만약 같지 않다면 인식되지 않습니다.  
**주의**: 나머지 행의 데이터가 헤더 행의 셀 수 보다 작은 경우 빈칸으로 채워지면 나머지 행의 데이터가 헤더 행의 셀 수 보다 많다면 초과 값은 무시됩니다.

**input**  
\| foo | bar |  
\| --- | --- |  
\| baz | bim |  

**output**  
| foo | bar |
| --- | --- |
| baz | bim |

## Task list items
* 예시로 설명하겠습니다.  

**input**  

\- [ ] foo  
\- [x] bar  

**output**  

- [ ] foo  
- [x] bar  

* 중첩될 수 있습니다. (아래 tap은 키보드의 tap을 입력한다.)

**input**  

\- [x] foo  
tap - [ ] bar  
tap - [x] baz  
\- [ ] bim  

**output**  

- [x] foo  
  - [ ] bar  
  - [x] baz  
- [ ] bim  

## Strikethrough

~~기호를 사용해서 새로운 강조 구문을 사용 할 수 있습니다.  

**input**  

\~~Hi~~ Hello, world!  

**output**  

~~Hi~~ Hello, world!  

## Autolinks

텍스트가 발견된 다음 유효한 도메인이나 이메일이 있을 경우 자동으로 링크됩니다.  

ex) www.naver.com  
ex) naver123@naver.com  

## Disallowed Raw HTML
GFM을 사용하면 HTML 출력을 렌더링할 때 다음 HTML 태그가 필터링되는 확장을 사용할 수 있습니다.  

**input**  

\<strong> <title> <style> <em>  

\<blockquote>  
(tap)\<xmp> is disallowed.  <XMP> is also disallowed.  
\</blockquote>  

**output**  

<strong> <title> <style> <em>  

<blockquote>  
   <xmp> is disallowed.  <XMP> is also disallowed.  
</blockquote>  

