- ```
  jQuery
    $(document).ready(function(){
      $('.scrollTol').click(function(e){
        e.preventDefault();
        var target = $(this).attr('href');  /*讀出herf值*/
        var targetPos = $(target).offset().top;  /*取出target的值*/
        $('body').animate({scrollTop: targetPos}, 1000) /*滾輪效果與時間*/
      });
  
      $(window).scroll(function(){
        var scrollPos = $(window).scroolTop();
        var windowHeight = $(window).height(); /*取得視窗高度*/
  
        $('.scrollTop').each(function(){
          var target = $(this).attr('href');
          var targetPos = $(target).offset().top;
          var targetHeight = $(target).outerHeight();
          if (targetPos - 1 <= scrollPos && (targetPos + targetHeight) > scrollPos){
            $('.scrollTop').removeClass('active')
            $(this).addClass('active');
          } else {
            $(this).removeClass('active')
          }
        });
  
        /*progess bar 滾輪滑到進度條才顯示出來*/
      });
    });
    
    $(document).ready(function () {     /*確保jQuery有被執行成功， */
      $('.class').hide(); /*css選擇器*/
      $('h1').hide();       /*html選擇器*/
      $('#box').hide();    /*id選擇器*/
      $(this).parent().toggleClass('') /*指定選取的東西. parent父元素*/
      $(this).parent().toggleClass('active').siblings().removeClass('active'); /*sibliings是選除了當前以外的同階層元素*/
      $(this).find().toggleClass('active'); /*選擇當前的子元素*/
  });
  $(document).ready(function () {
      $(".buttom").click(function () {
          $("h1").toggle() /*可以打開或關起來*/ /*HTML 如果用styly="display: none" 按一下就會變打開*/
              .fadeIn(Out / Toggle) /*預設隱藏的東西打開(關閉)*/
              .slideDown(Up / Toggle) /*滑動效果*/
              .css('weight', '500px') /*動態改長寬 通常*/
              .toggleClass('class') /*動態新增class*/
              .addClass('class')
              .removeClass('class')
              .html('<標籤>文字</標籤>')/*動態載入HTML要加標籤*/
              .text('你看不到我')/*動態載入 前面的選擇器要加入HTML標籤*/
              .attr('width', '250px'); /*動態新增HTML標籤屬性*/
                  .remove() /*通常用在購物網站上的購物車內容*/
              .on('click', '標籤', function (event) {  /*選擇所有標籤*/
                  event.preventDefault();
                  alert('有效');
              });
      });
  });
  
  $(document).ready(function () {
      $(連結的class).click(function (event) {
          event.preventDefault();      /*點了之後不會觸發事件*/ /*後面可以接效果*/
          $('.dropdown-open').stop().delay(毫秒).slideToggle(); /*delay可以依序出現 stop中斷目前動畫效果*/
  
          /*讓網頁回到最上面*/
          $('.top a').click(function (event) {
              event.preventDefault();
              $('html,body').animate({
                  scrollTop: 0            /*0是卷軸滾動到0 1000是毫秒*/
              }, 1000);
          });
    	};
  };
  
  // jQuery 遠端撈ajax語法
      $.ajax({
          type: 'GET',
          url: '要撈的JSON網址'
      success: function (data) {
              //成功的話就會傳到data變數
          }
      });
  ```