# javascript-server-time
서버시간 추출

    var xmlHttp;

    function srvTime(){

        if (window.XMLHttpRequest) {

            xmlHttp = new XMLHttpRequest(); // IE 7.0 이상, 크롬, 파이어폭스 등

            //헤더 정보만 받기 위해 HEAD방식으로 요청.
            xmlHttp.open('HEAD', window.location.href.toString(), false); // window.location.href.toString() or Target URL

            xmlHttp.setRequestHeader("Content-Type", "text/html");
            xmlHttp.send('');

            return xmlHttp.getResponseHeader("Date");   //받은 헤더정보에서 Date 속성만 적출

        }else if (window.ActiveXObject) {
            xmlHttp = new ActiveXObject('Msxml2.XMLHTTP');
            xmlHttp.open('HEAD',window.location.href.toString(),false);
            xmlHttp.setRequestHeader("Content-Type", "text/html");
            xmlHttp.send('');
            return xmlHttp.getResponseHeader("Date");
        }
    }

    var today = new Date(st);   // 한국 시간 +9

    alert(today);
