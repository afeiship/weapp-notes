# cover-btn
1. cover-view 里的透明层 button 并不能设置高度
2. 使用 position:absoute 思路也不行
3. 换个思路：(padding works fine)
   ```html
   <cover-view style="position:fixed; top:0; width:100%; height:100%; overflow:hidden;">
    <button style="width:100%; padding:1000px 0;">Content</button>
   </cover-view>
   ```