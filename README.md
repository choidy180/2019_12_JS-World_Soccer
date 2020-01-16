# JS-World_Soccer

+ MySql(DB)

주식별자(PK) = 다른 것과 자신을 구분할 수 있는 속성

>> 유일성, 최소성


테이블(RDB) = 관계형 자료구조

식별자 ▶ 스키마에서 찍어낸 인스턴스 구별

참조 ▶ 다른 테이블 참조 ▶ 다른테이블의 식별자를 가지고 와서 가져다 놓음

>> 외래 식별자(FK)

식별관계 ▶ 다른 테이블 식별자를 내 테이블에서 식별자로 쓰는 경우 ▶ FPK

비식별관계 ▶ 다른 테이블 식별자를 내 테이블에서 식별자로 쓰지 않는 경우


스키마 ▶ 클래스 ▶ 이걸로 뽑아낸게 


//메인페이지
router.get('/', function (req, res, next) {
  var sess=req.session;
  res.render('index', {title: "Soccor", page: 'main/main.ejs', sess:sess})
});


// 로그인 페이지 이동
router.get('/login', function (req, res, next) {
  var sess=req.session;
  res.render('index', { title: 'Soccor', page: 'user/login.ejs',sess:sess });
});


//회원가입 페이지 이동
router.get('/join', function (req, res, next) {
  res.render('index', { title: 'Soccor', page: 'user/join.ejs' });
});


//사진 페이지 이동
router.get('/picture', function (req, res, next) {
  res.render('index', { title: 'Soccor', page: 'content/picture.ejs' });
});


//비디오 페이지 이동
router.get('/video', function (req, res, next) {
  res.render('index', { title: 'Soccor', page: 'content/video.ejs' });
});


//랭크 페이지 이동
router.get('/rank', function (req, res, next) {
  res.render('index', { title: 'Soccor', page: 'content/rank.ejs' });
});
 
 
//로그아웃 요청
router.get('/logout', function(req, res, next) {
  var sess = req.session;
  sess.destroy();
  res.redirect('/')
});

