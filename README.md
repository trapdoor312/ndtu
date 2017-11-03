<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title> Yeutube</title>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
    <link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://bootswatch.com/superhero/bootstrap.min.css">
    <style>
        .video-title {
            overflow: hidden;
            text-overflow: ellipsis;
            overflow: hidden !important;
            white-space: nowrap;
            font-size: 20px;
        }
    </style>

</head>
<body background="white_wolf_painting-wallpaper-1366x768.jpg">
<div ng-app="myapp" ng-controller="myctrl">
    <div ng-if="video_da_chon" ng-click="tat_video()"
         style="position: fixed;z-index: 999;bottom: 300px;left: 560px;color: aliceblue;background:blue;width: 20px;text-align: center;cursor: pointer; ">
        &times;
    </div>
    <nav class="navbar navbar-inverse">
        <div class="container-fluid">
            <div class="navbar-header">
                <a class="navbar-brand" href="#">Yeutube</a>
            </div>
            <ul class="nav navbar-nav">
                <li class="active"><a href="#" name="home">Home</a></li>
                <li><a href="https://www.facebook.com/" target="_blank">facebook</a></li>
                <li><a href="https://mail.google.com/mail/u/0/#inbox" target="_blank">gmail</a></li>
            </ul>
            <form class="navbar-form navbar-left">
                <div class="form-group">
                    <input type="text" class="form-control" placeholder="search" ng-model="tim_kiem">
                    <button type="submit" class="btn btn-danger default">search</button>
                </div>
            </form>
        </div>
    </nav>
    {{tim_kiem}}
    <iframe width="560" height="315" src="{{video_da_chon}}" frameborder="0" allowfullscreen
            style="position: fixed;bottom: 0;z-index: 99"
    ></iframe>
    <div class="container">
        <div class="row">
            <div ng-repeat="video in videos| filter:{title : tim_kiem}" class="col-sm-3" ng-click="chon_video(video)">
                <img src="https://i.ytimg.com/vi/{{video.id}}/hqdefault.jpg" class="img-thumbnail" alt="">

                <div class="video-title">

                        <span>
                {{video.title}}
                      </span>

                </div>
            </div>
        </div>
    </div>

</div>
<SCRIPT>
    var app = angular.module("myapp", []);
    app.config(function ($sceProvider) {
        $sceProvider.enabled(false)
    })
    app.controller("myctrl", function ($scope) {
        $scope.chon_video = function (video) {
            $scope.video_da_chon = "https://www.youtube.com/embed/" + video.id + "?autoplay=true";
        };
        $scope.tat_video = function () {
            $scope.video_da_chon = '';
        };
        $scope.videos = [{"id": "gr0FXeNm_f8", "title": "Mr Siro - Em Gái Mưa (Piano Cover)"}, {
            "id": "Q6AhOSu-lPs",
            "title": "Giọng ải giọng ai 2 | Tập 1 full:Trấn Thành, Văn Mai Hương &quot;đơ toàn tập&quot; trước &quot;bản sao&quot; Hà Hồ"
        }, {
            "id": "ppFHU72_sqk",
            "title": "Phim Ca Nhạc Truy Tìm Kho Báu [Giải Cứu Tiểu Thư 4] | Hồ Việt Trung, Lilly Luta, Hứa Minh Đạt"
        }, {
            "id": "0ve3OMemd4w",
            "title": "Loa Phường Tập 38: Em gái mưa và bụi đời chợ bưởi | Phim hài 2017"
        }, {"id": "H1JqqUpMOc0", "title": "Đậu Phộng Tv - Tập 18 - Trung Thu Tìm Bạn Gái"}, {
            "id": "cxzmZX8VrFM",
            "title": "Đắng lòng phi công trẻ chưa kịp tỏ tình đã bị bạn gái gọi là em"
        }, {
            "id": "z5Jc7KiTLbs",
            "title": "TOULIVER X LÊ HIẾU X SOOBIN HOÀNG SƠN - NGÀY MAI EM ĐI 2017 | OFFICIAL LYRIC VIDEO"
        }, {"id": "wJnBTPUQS5A", "title": "Alan Walker - The Spectre"}, {
            "id": "hsGr-8Z4pFg",
            "title": "Muốn Nói [Official MV] | Khắc Việt"
        }, {"id": "iKzRIweSBLA", "title": "Ed Sheeran - Perfect [Official Lyric Video]"}, {
            "id": "nfs8NYg7yQM",
            "title": "Charlie Puth - Attention [Official Video]"
        }, {"id": "C70YRVND4EM", "title": "Rhymastic - Treasure (Official Lyric Video)"}, {
            "id": "eFCoYrLFtB4",
            "title": "Hương Tràm - Em Gái Mưa ( Anh Khang Cover )"
        }, {"id": "aNJm69M8dyM", "title": "Hương Tràm - Anh, Thế Giới Và Em (Lyric Video)"}, {
            "id": "lWrUIYj0gUA",
            "title": "EM GÁI MƯA - English Version - Cover by KYO YORK"
        }, {"id": "wgdkhUlCPp0", "title": "Hương Tràm - Em Gái Mưa (Behind The Scenes)"}, {
            "id": "-tFUH9z8DxI",
            "title": "Hương Tràm - Em gái mưa - Mr. Siro cover phong cách nam hay xuất sắc hay"
        }, {"id": "OcpO-cjIKYM", "title": "Cho Em Gần Anh Thêm Chút Nữa I OST I Hương Tràm"}, {
            "id": "NLWzwPFa2t8",
            "title": "Phim Hài Mới Nhất 2017: Lê Thị Dần, Chiến Thắng, Minh Tít - Cười Nghiêng Ngả"
        }, {
            "id": "epsLi7gKLdI",
            "title": "Hài Tết 2016 | Làng Ế Vợ 2 Full HD | Phim Hài Chiến Thắng, Bình Trọng"
        }, {"id": "23NAukRGGbU", "title": "Hài Chiến Thắng 2018"}, {
            "id": "x9gHHYhvhOI",
            "title": "Hài Tết 2017 | LÀNG Ế VỢ 3 FULL HD | Phim Hài Chiến Thắng, Bình Trọng, Trung Ruồi"
        }, {
            "id": "RQN99clDmzQ",
            "title": "Gái Xinh Bị Lừa Full HD | Phim Hài Tết 2017 Chiến Thắng, Quang Tèo Mới Hay Nhất"
        }, {
            "id": "zZjGBB5X3Z4",
            "title": "Đắp Mộ Cuộc Tình - Những Ca Khúc Để Đời Của QUANG LẬP | LK Nhạc Vàng Bolero Xưa Chọn Lọc"
        }, {
            "id": "y76fV_KwSsY",
            "title": "Hát gì mà hay vậy trời || Thật ngỡ ngàng khi nghe giọng hát cất lên || Quỳnh Trang, Thiên Quang"
        }, {
            "id": "7SqmMTP1Zfk",
            "title": "Tuyệt Đỉnh Song Ca Nhạc Vàng Bolero GÂY NGHIỆN | Quang Lập Lâm Minh Thảo - Đêm Gọi Người Yêu"
        }, {
            "id": "RCVupjxZba4",
            "title": "Nổi hết da gà khi giọng hát của cô ấy cất lên - Ngọc Nữ Bolero Phương Anh"
        }, {
            "id": "nWI8hcmsZ18",
            "title": "Bạn Chết Lặng Khi Nghe Ca Khúc Này - Cát Bụi Cuộc Đời | Nhạc Bolero Xưa Chấn Động Hàng Triệu Con Tim"
        }, {
            "id": "yxFe-16fM00",
            "title": "Liên Khúc Nhạc Vàng Hải Ngoại - Lưu Chí Vỹ ft Lưu Ánh Loan, Lê Như, Diễm Thùy, Quỳnh Trang"
        }, {
            "id": "YlMhspr2i1o",
            "title": "Người Khổng Lồ Xanh HD Thuyết Minh  Phim Hành Động Viễn Tưởng Mỹ Cực Hay"
        }, {
            "id": "C4kx3HSth64",
            "title": "Phim Hành Động Hay Nhất -CẢNH SÁT SIÊU ĐẲNG - PHIM HAY HẤP DẪN 2017"
        }, {
            "id": "Wghs9yLqEfw",
            "title": "Phim Chiếu Rạp Mới Nhất 2017 | Phim Chiếu Rạp Hài Hay Nhất Mọi Thời Đại"
        }, {
            "id": "SZ-gnEGvQnw",
            "title": "Chung Tự Đơn - Tổng hợp phim võ thuật, những trận solo hay nhất(p1)"
        }, {
            "id": "oOa1HdQsx28",
            "title": "BẢO VỆ KHO BÁU -  PHIM VÕ THUẬT Phim Hành Động 2017   Thuyết Minh"
        }, {
            "id": "t0VB_0YDZ1w",
            "title": "Minions dễ thương vui nhộn hài hước | Cười bể bụng | Giải Trí Cho Bé"
        }, {
            "id": "kUhCKeCOlKM",
            "title": "Liveshow Bolero Lệ Quyên, Quang Lê 2017 | Đêm Nhạc Duyên Phận Bolero Song Ca Hay Nhất"
        }, {
            "id": "YlDKXh5T7oc",
            "title": "Quang Lê - Xuân Này Con Về Mẹ Ở Đâu? (Nhật Ngân) PBN 76"
        }, {"id": "PaDqX64Q_v4", "title": "Sầu tím thiệp hồng - Quang Lê &amp; Lệ Quyên"}, {
            "id": "DQWanrdPBvY",
            "title": "Con Đường Xưa Em Đi - Quang Lê ft Lệ Quyên - Liveshow Xuân Phát Tài 2015"
        }, {
            "id": "a5LELE5_DRI",
            "title": "LỆ QUYÊN - QUANG LÊ BOLERO 2017 - Tuyệt Phẩm Nhạc Vàng Bolero Song Ca Lệ Quyên, Quang Lê"
        }, {
            "id": "BMobQWXESwg",
            "title": "Quang Lê &amp; Mai Thiên Vân - Gõ Cửa Trái Tim (Vinh Sử) PBN 92"
        }, {
            "id": "nrQnnbsSC5A",
            "title": "Hài Kịch &quot;Thần Chém, Thần Gió&quot; | PBN 116 | Chí Tài &amp; Trường Giang"
        }, {
            "id": "iJ0h1q7NTw4",
            "title": "Hài Hoài Linh | Một Trái Tim Hai Tiếng Hát - Hoài Linh, Trường Giang, Phi Nhung, Khánh Bình,"
        }, {
            "id": "h4bGVBO9Zy4",
            "title": "Hài Trường Giang Hay Nhất 2017 - Tuyển Tập Hài Trường Giang, Hoài Linh, Chí Tài, Long Đẹp Trai"
        }, {
            "id": "c-H7KD4k9II",
            "title": "Con Ma Đề - Cười Để Nhớ 3 - Hài Hoài Linh, Nhật Cường, Trường Giang Trấn Thành"
        }, {
            "id": "NbX-JZXIgok",
            "title": "Hài Kịch “Thần Tiên Cũng Nổi Điên” | PBN 119 | Trường Giang, Hoài Linh, Chí Tài, Thúy Nga, Hoài Tâm"
        }, {
            "id": "S1v6AROsjdQ",
            "title": "[HÀI 2017] Hoài Linh, Chí Tài, Trường Giang, Lâm Vỹ Dạ, Quách Ngọc Tuyên | Tác phẩm hài Ngang Trái"
        }, {"id": "JGwWNGJdvx8", "title": "Ed Sheeran - Shape of You [Official Video]"}, {
            "id": "87gWaABqGYs",
            "title": "Ed Sheeran - Galway Girl [Official Video]"
        }, {"id": "lp-EO5I60KA", "title": "Ed Sheeran - Thinking Out Loud [Official Video]"}, {
            "id": "nSDgHBxUbVQ",
            "title": "Ed Sheeran - Photograph (Official Music Video)"
        }, {"id": "_dK2tDK9grQ", "title": "Ed Sheeran - Shape Of You [Official Lyric Video]"}, {
            "id": "K0ibBPhiaG0",
            "title": "Ed Sheeran - Castle On The Hill [Official Video]"
        }, {
            "id": "uJybKFakNLg",
            "title": "quan vân trường phim chung tử đơn-phim thuyết minh mới nhất 2017"
        }, {"id": "N-naGhtvf-Y", "title": "KẺ VƯỢT NGỤC -   Phim Hành Động Kinh Điển 2017"}, {
            "id": "kKigMpK1yA4",
            "title": "Phim Hài Hoài Linh Chiếu Rạp Mới Nhất - Phim Hài Hoài Linh, Trường Giang 2017"
        }, {"id": "Se1y2R5QRKU", "title": "Top 10 Bruce Lee Moments"}, {
            "id": "tAnobOBpvS8",
            "title": "Top 10 phim võ thuật hay nhất của điện ảnh Hollywood  | Ten Tickers Theater 59"
        }, {
            "id": "WVOlmbFmIZQ",
            "title": "Pháp sư cũng phải bó tay với con ma Cương Thi này || Phim võ thuật  hay hài hước"
        }, {
            "id": "KqxTd995EYE",
            "title": "Trâu mẹ kéo hơn một 100 con Trâu Đực giải cứu con khỏi đàn Sư Tử , Sư Tử phải chạy lên cây trốn"
        }, {
            "id": "wkgSC3wrT9o",
            "title": "NASUS URF 1000Q Gần 7000 Máu Ai Dám Đến Gần | Trâu Best Udyr"
        }, {
            "id": "m9CpQTNw5hs",
            "title": "Trâu best udyr - Nasus hơn 1128 Q tại phút 29 - 9K tiền không thèm về!"
        }, {"id": "_g26BeWt7oo", "title": "Búfalos - Instintos Assassinos"}, {
            "id": "6dM926ydouk",
            "title": "CHỌI TRÂU Cảnh trâu húc chết chủ ở lễ hội Chọi Trâu Đồ Sơn 2017"
        }, {
            "id": "yeofbQxOKdE",
            "title": "Trâu Bất Ngờ Lâu Rồi Mới Gặp Lại &quot;Tool Hack&quot; Trong Liên Minh | Trâu Best Udyr"
        }, {
            "id": "W_17R08Ksbw",
            "title": "Chưa thấy trận nào nhà Chim Sẻ đẹp thế, Hồng Anh gục ngã với chỉ số Kill 0 tròn trĩnh"
        }, {
            "id": "3b8RVbxHFIo",
            "title": "Chim Sẻ và BiBi xuất sắc đả bại người Trung để vô địch thể loại 2 vs 2 Shang thuần tiễn"
        }, {
            "id": "vh5yuUDw9LI",
            "title": "C1T1 Solo Random Chim Sẻ vs Hưng Nhổn Ngày 13 09 2017"
        }, {
            "id": "VZb6A9TkBes",
            "title": "Trận 1 2vs2 Shang Chim Sẻ   Hehe vs ShenLong   Tiểu Thủy Ngư Ngày 15 09 2017"
        }, {
            "id": "fy2_46ZHFEI",
            "title": "2vs2 Chim Sẻ Đi Nắng - Hehe vs ShenLong - Tiểu Thủy Ngư   Ngày 15-09-2017"
        }, {"id": "cYuDCo1Pi8M", "title": "Solo Chim Sẻ vs ShenLong   Ngày 29-09-2017"}, {
            "id": "CevxZvSJLk8",
            "title": "Katy Perry - Roar (Official)"
        }, {"id": "dPI-mRFEIH0", "title": "Katy Perry - Bon Appétit (Official) ft. Migos"}, {
            "id": "0KSOMA3QBU0",
            "title": "Katy Perry - Dark Horse (Official) ft. Juicy J"
        }, {
            "id": "Um7pMggPnug",
            "title": "Katy Perry - Chained To The Rhythm (Official) ft. Skip Marley"
        }, {"id": "iGk5fR-t5AU", "title": "Katy Perry - Swish Swish (Official) ft. Nicki Minaj"}, {
            "id": "KlyXNRrsk4A",
            "title": "Katy Perry - Last Friday Night (T.G.I.F.) (Official)"
        }, {
            "id": "OFmWKCVp5tg",
            "title": "Tin Thể Thao 24h Hôm Nay (19h - 08/10): Kết Quả Lượt Trận Vòng Loại World Cup 2018 Khu Vực Châu Âu"
        }, {
            "id": "CEargL41Rfw",
            "title": "Tin Thể Thao 24h Hôm Nay (19h - 07/10): Tây Ban Nha Dành Vé Dự World Cup 2018,  Italia Đá Play Off"
        }, {
            "id": "B5o11W1PB_U",
            "title": "Tin Thể Thao 24h Hôm Nay (7h - 06/10): Play Off World Cup 2018 Syria Cầm Chân Australia"
        }, {"id": "B_tkYfNHvN8", "title": "Bản tin thể thao trưa - 08/10/2017"}, {
            "id": "2ZtKWcMqG30",
            "title": "Tin Thể Thao 24h Hôm Nay (7h - 09/10): Andrea Pirlo Tiết Lộ Thời Điểm Giải Nghệ"
        }, {
            "id": "YOh1sutR5jo",
            "title": "Tin Thể Thao 24h Hôm Nay (19h - 05/10):Harry Kane Tỏa Sáng Giúp Tuyển Anh Giành Vé Dự World Cup 2018"
        }, {
            "id": "lPSBTI-wBgs",
            "title": "Live 24/7 : Tuyển tập những ca khúc bolero cực hay của Quỳnh Trang"
        }, {"id": "SvA3HV0IjBY", "title": "[Live Stream] Superclip Tom &amp; Jerry Show Phần 2"}, {
            "id": "M2RkeRIcGlw",
            "title": "SIÊU NHÂN BIẾN HÌNH - Tập phim tổng hợp đoạn hay nhất của Siêu Nhân Hải Tặc"
        }, {
            "id": "5N2nGF0POrQ",
            "title": "Nonstop 2018 - Nhạc Sàn Cực Mạnh 2017 - Nhạc DJ Mới Nhất - Nhạc Trẻ Remix 2018 - Nonstop Việt Mix"
        }, {
            "id": "6ZEBZgdjqSk",
            "title": "Lisa Phạm- Khai Dân Trí Mới Nhất Ngày 09\\10\\2017"
        }, {"id": "JvpVXKKIMCI", "title": "Hà Anh Tuấn - Em À (Official Lyrics MV)"}, {
            "id": "J_ub7Etch2U",
            "title": "Sam Smith - Too Good At Goodbyes (Official Video)"
        }, {"id": "5Wiio4KoGe8", "title": "Maroon 5 - What Lovers Do ft. SZA"}, {
            "id": "CwLGro-dFWg",
            "title": "Charlie Puth – How Long [Official Audio]"
        }, {"id": "MBdVXkSdhwU", "title": "BTS (방탄소년단) 'DNA' Official MV"}, {
            "id": "HuoOEry-Yc4",
            "title": "TWICE「One More Time」Music Video"
        }, {
            "id": "EExwffrNBMg",
            "title": "Angelica Hale: 9-Year-Old Earns Golden Buzzer From Chris Hardwick - America's Got Talent 2017"
        }, {
            "id": "rk_qLtk0m2c",
            "title": "Darci Lynne: 12-Year-Old Singing Ventriloquist Gets Golden Buzzer - America's Got Talent 2017"
        }, {
            "id": "m0J-BwkQK4A",
            "title": "Celine Tam: 9-Year-Old Stuns Crowd with &quot;My Heart Will Go On&quot; - America's Got Talent 2017"
        }, {
            "id": "8ropWor8aAM",
            "title": "Darci Lynne: Kid Ventriloquist Sings With A Little Help From Her Friends - America's Got Talent 2017"
        }, {
            "id": "NwCjSclxZIo",
            "title": "Demian Aditya: Escape Artist Attempts Deadly Performance - America's Got Talent 2017"
        }, {
            "id": "yZm8znUvLHA",
            "title": "Darci Lynne: Young Ventriloquist Performs Diva Classic - America's Got Talent 2017"
        }, {
            "id": "N_wU29DMsQo",
            "title": "Phim chiếu rạp &quot; Bạn gái tôi là sếp&quot; Official Trailer #2"
        }, {
            "id": "4LcziYtp_34",
            "title": "Phim Tình Cảm Hay, Hài Hước Nhất- Chuyện Tình Đôi Đũa Lệch- Min and Max- Full HD Thuyết Minh"
        }, {
            "id": "PKeuQwKil3A",
            "title": "Phim hài &quot;Vệ sĩ, tiểu thư và thằng khờ&quot; Trailer"
        }, {
            "id": "qppUz89i7O8",
            "title": "Vijay Raaz All Comedy Scenes Run Movie HD - Kauwa Biryani | Kidney Nikal liya be | Choti Ganga"
        }, {
            "id": "BghvzAA_DHg",
            "title": "Katamarayudu (2017) Full Hindi Dubbed Movie | Pawan Kalyan, Shruti Haasan, Ali, Nassar"
        }, {
            "id": "Tmz_UgyWzbc",
            "title": "Kaashmora (2017) New Released Full Hindi Dubbed Movie | Karthi, Nayanthara, Vivek"
        }, {
            "id": "XizIavh7O8Y",
            "title": "Tướng mới ra mắt ở Việt Nam: RYOMA Thợ săn tiền thưởng trị giá 1 viên đá quý [Mua và test luôn]"
        }, {
            "id": "dA4dO7fmirk",
            "title": "Minecraft Ông Nội Kể Chuyện #7- SỰ TÍCH Ông Hàng Xóm BÍ ẨN!!"
        }, {
            "id": "MDsWt6iNuyE",
            "title": "NẾU KHỐI KIM CƯƠNG  CÓ CUỘC SỐNG TRONG MINECRAFT !!! (Minecraft Người Trông Trẻ)"
        }, {
            "id": "QLQ19_MbXD8",
            "title": "Roblox | KIA PHẠM BỊ BẮT CÓC???  - [Anti-Camp!] Captivator | KiA Phạm"
        }, {"id": "dmwUT974q3A", "title": "KHANHSKG ĐƯỢC NÂNG CẤP TRONG MINECRAFT"}, {
            "id": "mfY8P1Iqz8w",
            "title": "Troll NOOB Bằng Sát Nhân JASON Trong Minecraft!!"
        }, {"id": "Na-ya6tC6-Y", "title": "Liên Quân Mobile: Tùng XO trở lại, kéo rank miễn phí"}, {
            "id": "ot3wAWjCVsM",
            "title": "🔴 SKT T1 Faker Live Stream LOL -09/10 Translation EN | Hide on bush | SK텔레콤 T1 / SK Telecom T1"
        }, {"id": "1y-dyFlf0XI", "title": "Liên Quân Mobile | TuấnHC Tung Hoành Rank Bạch Kim"}, {
            "id": "1i_ULsVyZoY",
            "title": "Come Back - Quang Brave !"
        }, {
            "id": "nPCm9AWrufY",
            "title": "GTA 5 EPIC FAILS &amp; WINS, MODS, HEISTS &amp; DLC SPENDING SPREE - LIVE 24/7 WITH BEST OF HIKEPLAYS &amp; GTA5"
        }, {
            "id": "wyf-c5WjFME",
            "title": "🔴SKT T1 Faker Live Stream LOL 09/10 | Hide on bush | SK텔레콤 T1 | SKT T1 | 리그 오브 레전드"
        }

        ];
    });
</SCRIPT>
<center><a href="#home">đầu trang </a></center>
</body>
</html>
