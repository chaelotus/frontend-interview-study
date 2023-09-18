# CSR과 SSR의 차이는 무엇인가요?
csr(client side rendering)은 렌더링이 클라이언트 쪽에서 일어납니다. 서버에서 요청을 받으면 클라이언트에게 파일을 보내줍니다. 클라이언트는 그것을 받아 렌더링을 시작합니다. 
ssr은 서버쪽에서 렌더링 준비를 끝 마친 상태로 클라이언트에게 전달하는 방식입니다.

따라서  csr의 경우 모든 파일을 한번에 불러오고 ssr은 필요한 부분의 파일만 불러오게 되므로 첫 페이지 로딩시간이 ssr이 더 빠릅니다.
그 뒤 나머지 로딩 시간은 첫페이지를 로딩 한 후, csr는 이미 첫 페이지를 로딩할 때 나머지 부분을 구성했기 때문에 빠릅니다.
반면 ssr은 첫 페이지 로딩한 과정을 정확하게 다시 실행하여 더 느립니다.

검색엔진은 크롤러로 웹 사이트를 읽습니다. csr은 자바스크립트를 실행 시켜 동적으로 컨텐츠가 생성되기 때문에 자바스크립트가 실행되어야 metadata가 바뀝니다. ssr은 애초에 서버 사이드에서 컴파일되어 클라이언트로 넘어오기 때문에 크롤러에 대응하기 용이합니다.


<br/>
<br/>

## ⚙️ 용어 정리
- 렌더링 : UI를 화면에 표시하는 과정
- metadata : 데이터에 대한 추가적인 정보를 제공하거나 설명하는 데이터입니다.  
   검색 엔진과 관련하여 메타데이터는 웹 페이지, 문서 또는 다른 정보 자원에 대한 정보를 제공하고 검색 결과의 정확성과 품질을 향상시키는 데 중요한 역할을 합니다.  

   1. 메타 태그(Meta Tags): HTML 문서의 <head> 섹션에 포함되는 메타 태그를 사용하여 웹 페이지의 제목, 설명, 키워드 등을 제공합니다. 이러한 정보는 웹 검색 엔진이 해당 페이지를 적절하게 색인화하고 검색 결과에 표시하는 데 사용됩니다.
    ```js
    <head>
        <meta name="description" content="이 웹 페이지에 대한 간단한 설명입니다.">
        <meta name="keywords" content="검색, 엔진, 메타데이터">
        <title>웹 페이지 제목</title>
    </head>
    ```

    2. 링크 관계 메타데이터(Link Relationship Metadata): <link> 태그를 사용하여 웹 페이지와 관련된 다른 자원에 대한 정보를 제공합니다. 예를 들어, RSS 피드 또는 스타일 시트와의 관계를 명시할 수 있습니다.
    ```js
    <link rel="alternate" type="application/rss+xml" title="RSS 피드" href="/rss-feed.xml">
    <link rel="stylesheet" type="text/css" href="styles.css">
    ```
    3. OG 메타데이터(Open Graph Metadata): 소셜 미디어 플랫폼에서 웹 페이지를 공유할 때 사용되는 메타데이터 형식으로, 웹 페이지의 제목, 설명, 이미지 등을 지정합니다.
    ```js
    <meta property="og:title" content="웹 페이지 제목">
    <meta property="og:description" content="웹 페이지에 대한 설명입니다.">
    <meta property="og:image" content="이미지 URL">
    ```
    4. JSON-LD: 구조화된 데이터를 표현하기 위한 JSON 형식의 메타데이터입니다. 주로 스키마(구조화된 데이터 표준)를 사용하여 웹 페이지의 내용을 설명하고 검색 엔진에게 의미 있는 정보를 제공합니다.
    ```js
    {
    "@context": "http://schema.org",
    "@type": "Product",
    "name": "상품 이름",
    "description": "상품 설명",
    "brand": "브랜드 이름"
    }
    ```
- 크롤러 : 웹 페이지를 읽어서 데이터베이스를 구축하는 프로그램입니다.