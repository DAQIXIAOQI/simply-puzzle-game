# simply-puzzle-game
今天来写个拼图游戏~！
##功能简述<br>
1.拖拽交换，可与其余所有碎片交换<br>
2.提供3幅画<br>
3.完成后弹框并显示所用时间<br>
##逻辑与交换方法<br>
当用户拖拽某一张图后，每mousemove一次都会调用getMin（）函数，会返回与该图片最接近的图片序号（算法是保存所有图片的top、left属性，对应相减并平方再开根号）。
当用户mouseup的时候通过缓冲运动交换两张图片的位置，并通过removechild、appendchild等操作交换两者文档流的位置。最后调用ifinsh（），判断是否有完成，
方法是从每一个li>img中提取src，再通过正则表达式提取图片序号，最后放进for循环判断图片序号是否为正确的序号。若正确，则弹框，游戏结束。
