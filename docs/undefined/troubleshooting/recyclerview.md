# RecyclerView 동작 안 하는 현상 (빈 화면만 표시됨)

원인

```
Recycler 앞의 Item이 match_parent여서 이미 부모의 영역을 다 써버림.
따라서, Recycler뷰가 부모영역 밖에서 표시되어서 마치 빈 화면만 표시된것 처럼 보임
```
