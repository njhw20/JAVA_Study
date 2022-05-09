## 단지번호 붙이기

BFS를 이용해서 구현</br></br>

이중 for문을 돌면서 만약 방문하지 않았고, 집이 있는 곳이라면 큐에 넣는다</br>
이때 cnt를 하나 더 해주는데, 이 cnt는 단지의 개수이다</br>
while문을 이용해 큐가 빌 때까지 상하좌우를 돌면서 집이 연결되어있는지 확인하는데</br>
while문 안에서 area++ 을 하면 각 단지 내 집의 수를 구할 수 있다</br></br>

집의 개수는 오름차순으로 정렬하여 출력해야하므로</br>
ArrayList에 넣고, Collections.sort() 를 이용해 정렬된 값을 출력한다
</br></br></br>
</br></br></br>



## 토마토

역시 BFS를 이용해서 푸는 문제</br></br>

만약 애초에 모든 토마토가 익어있다면 0을 출력해야하는데,</br>
익지 않은 토마토의 개수를 cant로 두고, cant가 0이라면 0을 출력하고 return</br>
토마토가 하나도 없는 경우는 없기 때문에 바로 return해도 된다</br></br>

만약 입력을 받을 때 토마토가 이미 익어있다면, 그 토마토를 큐에 넣고</br>
while문을 돌면서 상하좌우를 움직여 토마토가 익음을 표현</br></br>

![image](https://user-images.githubusercontent.com/50469773/159231902-1b9d07f7-752e-461f-8f8d-2721f968e282.png)
</br></br>

만약 while문을 빠져나온 후, dist배열을 확인했을 때 dist[i][j]==-1이고, 즉 갱신되지 않았고</br>
tomato[i][j]!=-1 이라면, 즉 토마토가 존재하는 곳이라면 익지 않은 토마토가 있다는 뜻이니</br>
-1을 출력하고 return을 한다</br></br>

또한 원하는 결과는 토마토가 모두 익은 최소 일수이므로 dist[i][j] 값 중 가장 큰 값을 출력</br>
최소 일수이지만 토마토가 모두 익어야하니까!
</br></br></br>
</br></br></br>
## 이분그래프
이분 그래프는 인접한 정점을 다른 색깔로 칠하는데 그래프의 정점을 2가지의 색으로만 칠할 수 있는 그래프</br></br>

만약 1-2, 2-3, 3-4가 정점이라면</br>
![image](https://user-images.githubusercontent.com/50469773/159232384-1a322eba-c4de-4231-bd7c-4a24ec6c8c04.png)
</br>
이렇게 표현할 수 있으므로 이 경우는 이분 그래프라고 할 수 있다</br></br>

이중 ArrayList를 만들어서 정점을 추가해놓고 while문을 돌면서 현재 정점과 인접한 정점을 칠하는데</br>
현재 정점이 1이고 인접 정점을 방문하지 않았다면 2로,</br>
현재 정점이 2이고 인접 정점을 방문하지 않았다면 1로 칠한다</br></br>

만약 현재 정점과 인접 정점의 색깔이 같다면 이분 그래프가 아니므로 NO를 출력하고</br>
break를 걸어서 while문을 탈출하게 한다</br></br>

여기서 만약 for(int i=1; i<=v; i++) 를 하지 않으면</br>
인접한 정점이 없는 경우에 문제가 생기므로 for문을 돌면서 모든 정점을 체크해줘야한다</br>
![image](https://user-images.githubusercontent.com/50469773/159232675-74e31972-7031-4506-aa28-63bf368a2710.png)
</br></br>
***
처음에 1-2, 2-3, 3-4에서 결과는 YES여야하는데 NO로 나왔었는데</br>
graph.get(a).add(b)를 하는데서 여기는 무방향 그래프이니</br>
graph.get(b).add(a)까지 해줘야하는데 하나만 했더니 잘못된 결과 도출</br></br>

방향 그래프일 때 무방향 그래프일 때 잘 생각해야함
</br></br>