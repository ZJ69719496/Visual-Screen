# Visual-Screen
自适应浏览器的大数据展示WEB页面 研究了好久，
该页面可以自适应浏览器宽高，内部元素不会因为浏览器大小变化而导致位置偏移
现在分享该自适应的方法给大家（之前一直都是动态改变 height width 和 left top，这种方法很浪费性能）

在body里面设置一个div容器  然后在这个容器内部写各种元素
只要设置好每个内部元素的 left top width height（不要用百分比的值  直接用px就可以了  然后设置文档页面大小变化的事件）

//随着浏览器窗体缩放页面
function scale(SCALE) {
      var winWidth = screen.width;
      var winHeight = screen.height;
      var docWidth = $(window).width();
      var docHeight = $(window).height();
      var wp = docWidth / winWidth / SCALE;//宽度缩放比例
      var hp = docHeight / winHeight / SCALE;//高度缩放比例
      var $div = $('#content');
      $div.css('transform', "scale(" + wp + "," + hp + ")");
      $div.css('transform-origin', "0 0");
}

正常页面  
![正常页面](https://github.com/ZJ69719496/Visual-Screen/blob/master/s1.png)  
  
变窄  
![变窄](https://github.com/ZJ69719496/Visual-Screen/blob/master/z.png)  
  
变宽  
![变宽](https://github.com/ZJ69719496/Visual-Screen/blob/master/k.png)  

正常页面2  
![正常页面2](https://github.com/ZJ69719496/Visual-Screen/blob/master/s2.png)  
