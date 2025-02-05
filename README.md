<h1 id="mycomix">myComix</h1>

<p><br></p>

<h2 id="phpcomicsviewer">PHP Comics Viewer</h2>

<p><br>
PHP7 and later versions and php-zip, php-gd installed webservers required.</p>

<p>Modify config.php to suit your environment. You can set the two variables below.</p>

<pre style="background-color: #DDDDDD;"><code class="php language-php">$base_dir = "/myComix"; //Absolute path with comics
$maxview = "18"; //Number of Mangas/Comics to show on one page (folders are shown on one screen only for this number)
</code></pre>

<p>If you are using a safari browser such as an iPhone, you cannot save the automatic bookmark by clicking Go Back/Go To Other Pages.<br>
If you turn the safari to the background, such as returning to home, the bookmark is stored, so it is recommended that you store the bookmark manually as much as possible.</p>

<p><br></p>

<hr />

<p><br></p>

<h2 id="">Features</h2>

<p></p>

<ul>
<li>Two-Sided File Split</li>
</ul>
<ul>
<li>Slide to full screen</li>
</ul>
<ul>
<li>ScrollView Webtoon</li>
</ul>
<ul>
<li>Viewing PDF Files</li>
</ul>
<ul>
<li>Support for uncompressed manga folders</li>
</ul>
<ul>
<li>Thumbnail support with first image of file</li>
</ul>
<ul>
<li>Folder Thumbnail Support</li>
</ul>
<ul>
<li>Manual bookmark support</li>
</ul>
<ul>
<li>Support for Automatic Storage in Reading</li>
</ul>

<p><br></p>

<h2 id="">Typical Issues</h2>

<p></p>

<ul>
<li>If bookmark or thumbnail generation is not possible, check permissions.</li>
</ul>

<p>You must have write permission on the folder to create a thumbnail. in most cases must be given 707 to 777 <br />
<code>chmod -R 777 /YourComicFolder</code> <br />
<code>chmod -R 777 /myComixFolder</code> <br />
<br></p>

<ul>
<li>The response is very slow when using rclone.</li>
</ul>

<p>This is because directory checks are frequent to distinguish between folders with and without subfolders. <br />
It is also very slow when generating thumbnails, but this problem is solved once you make them. <br />
You can preface the folder name with "rclone_", or you can create a thumbnail and set a subdirectory confirmation exception with is_remote settings on the administrator page. <br />
<br></p>

<ul>
<li>Nothing appears on the screen.</li>
</ul>

<p>This usually occurs because you do not have permission or the PHP module is not installed. <br />
<code>php-zip</code>, check if the <code>php-gd</code> module is loading.</p>

<p><br></p>

<hr />

<p><br></p>

<h2 id="-1">Changelog</h2>
<p>(I ain't gonna translate that sorry)
<p><br></p>

<ul>
<li>index 0.488 </li>
</ul>

<p>
github에 올라온 이슈에 대응. dir경로에 %2F..(/..)을 넣어 상위 디렉토리를 호출하면 호출되는 문제를 수정.<br>
dir에서 %2F..을 삭제하도록 했음. 마이코믹스에서 .. 경로를 사용하지 않으므로 다른 문제는 없으리라 생각됨.
</p>


<p><br></p>

<ul>
<li>index 0.487 </li>
</ul>

<p>
새파일체크를 켜둔 경우, new 마크가 붙는 폴더를 맨 앞으로 모아 정렬한다.
</p>


<p><br></p>

<ul>
<li>index 0.486 </li>
</ul>

<p>
PHP만화 다운로더를 이용하는 경우 tmp폴더가 생성되는데, 목록에서 이 폴더를 제외한다.
</p>


<p><br></p>

<ul>
<li>index 0.485 </li>
</ul>

<p>
네이버 만화의 경우 높이 20픽셀짜리 단색라인이 만화 중간중간 들어가는 경우가 있는데,<br>
기존 뷰어에서 최소높이가 지정되어있어 하얀박스 안에 색 라인이 들어가게 되는 문제가 있었다.<br>
이 문제를 개선함.
</p>


<p><br></p>

<ul>
<li>index 0.484 </li>
</ul>

<p>
기본정렬방식 개선
</p>


<p><br></p>

<ul>
<li>index 0.483 </li>
</ul>

<p>
기본정렬 역순 추가
</p>


<p><br></p>

<ul>
<li>index 0.482 </li>
</ul>

<p>
만화책 리스트에 정렬기능 추가. 이는 만화책 목록에서만 작동하며, 저장되지 않는다.<br>
이 기능은 새파일, 큰파일을 빠르게 찾기 위하여 만들어진 기능이므로 뷰어화면에도 바뀐 정렬순서는 적용되지 않는다.
</p>


<p><br></p>

<ul>
<li>index 0.481 </li>
</ul>

<p>
리모트모드에서 압축되지 않은 만화를 볼 수 없었던 문제 수정
</p>


<p><br></p>

<ul>
<li>index 0.480 </li>
</ul>

<p>
새파일체크기능을 폴더별로 설정할 수 있도록 수정<br>
설정되지 않은 경우, 기본적으로 새파일을 체크한다.
</p>


<p><br></p>

<ul>
<li>index 0.479 </li>
</ul>

<p>
0.478 업데이트에서 폴더에 파일이 하나만 있는 경우 new 안뜨는 버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.478 </li>
</ul>

<p>
폴더의 마지막 파일을 읽지 않은 경우, 폴더리스트에 노란색 new 뱃지가 붙는다.<br>
웹툰을 읽을 때, 아직 덜 읽었는지 여부/새 파일이 받아졌는지 여부를 알 수 있다.<br>
위 기능은 디렉토리를 여러차례 반복하여 검색하므로 리모트설정된 폴더에서는 작동하지 않는다.
</p>


<p><br></p>

<ul>
<li>index 0.477 </li>
</ul>

<p>
0.476 업데이트가 제대로 작동하지 않는 버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.476 </li>
</ul>

<p>
폴더에서 읽은 파일 중 제일 뒷순번 파일을 기록한 후 리스트 맨 위에 보여준다. 웹툰 등을 이어보기 편리하게 하기 위한 장치<br>
마지막으로 읽은 파일을 누른 후, 다음파일로 넘어가면 읽지않은 파일을 읽을 수 있다.<br>
파일 전부에 대하여 읽었는지 여부를 기록하지 않고 마지막 파일만 기록하는 방법을 택한 이유는 저장데이터가 지나치게 커지는 것을 막기위함이다.
</p>


<p><br></p>

<ul>
<li>index 0.474 </li>
</ul>

<p>
PDF출력방식 수정. PDF북마크 가능. 키보드나 스와이프로 페이지이동이 가능하다.<br>
0.475에서 테스트용 버튼 삭제
</p>


<p><br></p>

<ul>
<li>index 0.473 </li>
</ul>

<p>
PDF출력품질 수정. 기존 수정이 메모리를 너무 차지하여 리스프링이 일어남에 따라 출력품질을 낮췄다.<br>
안드로이드의 경우 인라인PDF출력이 불가능하여 번거로운 방법을 사용하고 있음에 양해를 구한다.<br>
당분간은 PDF출력과 관련하여 업데이트가 잦을 예정이다.
</p>


<p><br></p>

<ul>
<li>index 0.472 </li>
</ul>

<p>
PDF출력품질 수정<br>
</p>


<p><br></p>

<ul>
<li>index 0.471 </li>
</ul>

<p>
PDF파일을 모바일에서도 직접 볼 수 있도록 모듈을 교체.<br>
다만 매우 느리며, 아직 스크롤 보기만 지원한다.
</p>


<p><br></p>

<ul>
<li>index 0.470 </li>
</ul>

<p>
PDF와 이미지 폴더의 제목줄이기 함수가 사용되지 않은 것 수정<br>
PDF파일의 확장자가 대문자가 섞인 경우 목록이 제대로 출력되지 않던 문제 수정
</p>


<p><br></p>

<ul>
<li>index 0.469 </li>
</ul>

<p>
PC의 경우 PDF파일을 지원, 휴대폰에서는 PDF를 다운로드 받도록 안내한다.<br>
리스트커버사용시 딜레이 발생은 광고차단앱을 끄면 해소된다.<br>
이미지 폴더의 경우, 다음파일 이전파일을 지원하지 않고 있던 것을 발견하여 수정했다.
</p>


<p><br></p>

<ul>
<li>index 0.468 </li>
</ul>

<p>
리스트커버이미지 사용설정시 목록 2단으로 출력.<br>
현재 리스트커버 이미지사용시 이유를 알 수 없는 딜레이가 심하게 발생하므로 사용하지 않는 것을 권장함.<br>
그 외, 몇화인지가 괄호 안에 들어간 경우에 대응하기 위해 제목을 줄이는 함수에 약간의 수정이 있었다. 
</p>


<p><br></p>

<ul>
<li>index 0.467 </li>
</ul>

<p>
UI수정 과정에서 발생한 일부 버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.466 </li>
</ul>

<p>
GIF지원
</p>


<p><br></p>

<ul>
<li>index 0.465 </li>
</ul>

<p>
지난 업데이트에서 커버이미지를 설정할 수 있도록 했으나 리스트 화면에서 높이가 달라지는 관계로 화면이 미려하지 못한 문제가 있었다.<br>
이 문제를 해결할 방법을 고민했으나 부트스트랩에 익숙하지 않아 당장 해결하기 어려우므로 목록에서 커버이미지를 썸네일 형태로 보여줄지 여부와 폴더커버이미지를 보여줄지 여부를 분리하여 설정하도록 했다.<br>
폴더커버를 사용으로 설정하면, 만화책 목록이 나오는 페이지에서 상단에 커버이미지를 출력하며, 리스트커버를 사용으로 설정하면, 디렉토리 목록의 제목 옆에 커버이미지가 작게 표시된다.<br>
뷰어에서 해당 파일의 첫번째 이미지를 대표이미지로 교체 설정할 수 있다.
</p>


<p><br></p>

<ul>
<li>index 0.46 </li>
</ul>

<p>
버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.46 </li>
</ul>

<p>
폴더 커버이미지 사용여부를 관리자페이지에서 선택할 수 있다. 설정하는 경우, 만화책파일이 있는 폴더의 [cover].jpg파일을 출력한다.<br>
만일 커버이미지 파일이 없는 경우, 만화 폴더에 진입시 자동으로 폴더의 첫번째 파일의 썸네일을 [cover].jpg 파일로 저장한다.<br>
이 커버이미지는 사용자가 교체할 수 있다. (파일명은 모두 소문자로 써야한다.)
</p>


<p><br></p>

<ul>
<li>index 0.459 </li>
</ul>

<p>
총 북마크 갯수, 총 자동저장 갯수를 관리자페이지에서 수정할 수 있도록 했다.
</p>


<p><br></p>

<ul>
<li>index 0.458 </li>
</ul>

<p>
뷰어에서 목록으로 나갈 때, 페이지 유지 안되던 문제 수정
</p>


<p><br></p>

<ul>
<li>index 0.457 </li>
</ul>

<p>
북마크 관련 버그 수정<br>
북마크 삭제시 북마크가 날아가버리는 치명적인 버그 수정<br>
자동저장된 북마크도 삭제할 수 있도록 수정
</p>


<p><br></p>

<ul>
<li>index 0.455 </li>
</ul>

<p>
뷰어를 떠날 때, 북마크가 자동저장된다(오류가능성이 있다). 자동북마크는 세개까지 저장하며, 삭제할 수 없다.(느낌표 표시)<br>
북마크 자동저장기능을 도입함과 동시에, 북마크 불러오기 화면을 조금 바꾸게 되었다.
</p>


<p><br></p>

<ul>
<li>index 0.454 </li>
</ul>

<p>
config.php파일의 설정을 관리자페이지에서 수정할 수 있도록 함
</p>


<p><br></p>

<ul>
<li>index 0.45 </li>
</ul>

<p>
압축되지 않은 만화책 폴더를 압축된 파일처럼 처리.<br>
폴더 01, 02, 05, 07 파일 03.zip, 04.zip, 06.zip 이 있는 경우, 01-02-03.zip-04.zip-05-06.zip-07 순서로 정렬한다.<br>
0.451에서 이미지폴더 못읽는 버그 바로 수정
</p>


<p><br></p>

<ul>
<li>index 0.446 </li>
</ul>

<p>
파일 정렬방식 개선
</p>


<p><br></p>

<ul>
<li>index 0.445 </li>
</ul>

<p>
PC에서 작은 이미지 여러개가 한줄로 나오는 문제 수정
</p>


<p><br></p>

<ul>
<li>index 0.444 </li>
</ul>

<p>
뷰어화면 상단 내비바 정리. 기어버튼 누르면 북마크와 밝기조절 메뉴가 뜨도록 수정함<br>
전체화면보기 모드의 북마크 동작 방식 수정. 전체화면 모드가 아닐 때에도 스크롤 위치 확인하여 북마크 정상동작
</p>


<p><br></p>

<ul>
<li>index 0.441 </li>
</ul>

<p>
뷰어 화면에서 화면 밝기를 위 아래 각 5단계로 조절할 수 있도록 수정.<br>
각 단계마다 대비는 10%(0.1)씩, 밝기는 4%(0.04)씩 각 조절된다.<br>
0.442 - 안드로이드 전체화면모드에서 밝기조절이 유지되지 않던 버그 수정
</p>


<p><br></p>

<ul>
<li>index 0.434 </li>
</ul>

<p>
lazyload 개선
</p>


<p><br></p>

<ul>
<li>index 0.42 </li>
</ul>

<p>
뷰어에 밝기와 대비를 높여주는 버튼을 넣었다. 스캔만화를 볼 때 효과적이다.
</p>


<p><br></p>

<ul>
<li>index 0.411 </li>
</ul>

<p>
아주 미묘하게 속도 향상. 당분간은 기능추가 등의 업데이트보다 작동방식을 최적화 할 예정이다.
</p>


<p><br></p>

<ul>
<li>index 0.41 </li>
</ul>

<p>
update.php 파일이 변경되었다.<br>
기존에 업데이트의 정상처리 여부를 가져온 용량/기록한 용량으로 체크하였는데, 권한문제로 기록이 되지 않았음에도 기록한 용량은 정상으로 표시되고 있다는 문제가 있었다.<br>
그리하여 기록한 파일의 해시값과 가져온 파일의 해시값을 비교하는 방식으로 정상처리여부 확인방법을 바꿨다.<br>
혹시 업데이트를 눌렀을 때 해시값을 비교하는 화면이 나오지 않는다면 수동으로 새파일로 교체하라.
</p>


<p><br></p>

<ul>
<li>index 0.407 </li>
</ul>

<p>
사용자 그룹관리 안되던 것 수정. <br>
깃허브에 수정된 파일을 올렸다고 굳게 믿고 있었는데, 안올린걸 몇시간이 지나 알았다..
</p>


<p><br></p>

<ul>
<li>index 0.404 </li>
</ul>

<p>
bookmark.json파일과 user.php 파일을 src 라는 하위폴더를 만들어 그 아래에 위치하도록 수정.<br>
깃허브에 파일 올리다가 실수하는 일이 없도록 수정했다. 사용자는 그냥 사용하면 저절로 폴더를 만들고 파일을 이동한다.
</p>


<p><br></p>

<ul>
<li>index 0.402 </li>
</ul>

<p>
보안 향상. 기존사용자는 업데이트를 위해 사용자그룹수정을 한번 실행하라.
</p>


<p><br></p>

<ul>
<li>index 0.4 </li>
</ul>

<p>
북마크 저장시 읽던 모드를 함께 저장하여 다른 사람이 읽기모드 바꿔도 무관하게 수정(기존 북마크는 이용가능)<br>
파일 정렬방식 다소 수정하여 띄어쓰기와 언더바 제거하고 정렬하도록 수정.
</p>

<p><br></p>

<ul>
<li>index 0.395 </li>
</ul>

<p>급작스런 버그수정 및 파일명에 띄어쓰기대신 언더바(_)가 있는 경우 띄어쓰기가 있는 파일보다 먼저 정렬되는 문제 수정</p>

<p><br></p>

<ul>
<li>index 0.393 </li>
</ul>

<p>북마크 처리방식 변경, 이제 북마크버튼 누르면 북마크되는 페이지가 표시된다.</p>

<p><br></p>
<ul>
<li>index 0.392 </li>
</ul>

<p>폴더이름에 "."이 있어도 권한설정 가능</p>

<p><br></p>
<ul>
<li>index 0.39 </li>
</ul>

<p>로그인처리 세션으로 변경, 그 밖의 소소한 수정.</p>

<p><br></p>

<ul>
<li>index 0.36 </li>
</ul>

<p>admin페이지에서 버전업 정보를 읽을 수 있도록 함. admin페이지 변경.</p>

<p><br></p>

<ul>
<li>index 0.35 </li>
</ul>

<p>페이지이동 PC에서 드롭다운되던 것 위로 드롭업되도록 수정, 관리자페이지에서 폴더를 리모트지정할 수 있도록 수정</p>
