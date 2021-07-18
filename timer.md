1. 제목과 색 바꾸기 (색 : brown, 버튼 색 : amber)
2. 변수 선언하기
```
var _icon = Icons.play_arrow;
var _color = Colors.amber;

style:TextStyle(fontSize:80)
```

3. body밑에다가 
``` 
bottomNavigatorBar: BottomAppBar(
  child : Container(
    height : 80
  )
),
```

4. 버튼은
```
child: Icon(_icon),
backgroundColor : _color,
), floatingActionButtonLocation : FloatingActionButtonLoaction.centerDocked

```

5. if문 사용
```
if(_icon == Icons.play_arrow) {
      _icon = Icons.pause;
      _color = Colors.grey;
    }
    else{
      _icon = Icons.play_arrow;
      _color = Colors.amber;
    }
```

