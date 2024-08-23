<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manager Search Tool</title>
    <style>
        body {
            font-family: "Pretendard ExtraBold", Arial, sans-serif; /* 폰트를 Pretendard ExtraBold로 지정 */
            margin: 50px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
            font-family: inherit; /* 부모 요소(body)의 폰트를 그대로 사용 */
        }
    </style>
</head>
<body>

    <h1>농협손보 GA 매니저를 검색합니다.(by.다솜GA)</h1>
    <input type="text" id="searchText" placeholder="Enter text to search...">
    <button onclick="search()">검색하기!</button>

    <h2>Result:</h2>
    <div id="result"></div>

    <script>
        const managerData = {
            "이정은 매니저 / 010-4110-5785": ["KS자산관리", "원금융", "굿리치", "보험몰", "인코미디어"],
            "이우선 매니저 / 010-4070-6986": ["에즈", "엑셀", "보험닷컴", "한국지에이", "더블유", "한국GA금융"],
            "장혜진 매니저 / 010-6576-9589": ["메가", "지에이코리아", "GAK", "한국보험금융", "한보금", "더좋은", "유어즈", "KMI", "케이엠아이", "더베스트"],
            "이원규 매니저 / 010-2362-9424": ["피플", "피플라이프", "한화생명금융", "한화금융", "한금서", "신한금융", "리더스에셋", "삼성금융", "AIG", "에이아이지", "지에이스타"],
            "곽지영 매니저 / 010-8402-6109": ["인카", "지금융", "영진", "세안", "밸류", "ABA", "에이비에이", "서울법인"],
            "강하나 매니저 / 010-4635-9917": ["글로벌금융", "푸른신호등", "에프엠", "FM", "엠금융", "M금융", "A+", "에이플러스", "베라", "인포유", "스카이블루", "프라임"],
            "서유미 매니저 / 010-7547-3088": ["케이지에이", "KGA", "AT", "에이티에셋", "아너스", "한화라이프랩", "에이원", "하나금융", "유퍼스트", "미래에셋"],
            "조영매 매니저 / 010-7765-8460": ["인슈코아", "미래와행복", "FC금융", "인코리아", "비큐러스", "에인스", "마이금융", "IT마이맥스"]
        };

        function search() {
            const searchText = document.getElementById('searchText').value.toLowerCase();
            let result = '정확한 대리점 명을 입력해주세요';

            for (const manager in managerData) {
                if (managerData[manager].some(keyword => searchText.includes(keyword.toLowerCase()) || keyword.toLowerCase().includes(searchText))) {
                    result = manager;
                    break;
                }
            }

            document.getElementById('result').innerText = result;
        }
    </script>

</body>
</html>
