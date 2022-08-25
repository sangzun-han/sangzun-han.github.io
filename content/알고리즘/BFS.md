---
emoji: 😂
title: 'BFS'
date: '2022-08-22 00:00:00'
author: sangzun
tags: 알고리즘
categories: 알고리즘
---

### 백준 1697. 숨바꼭질

```markDown
수빈이의 위치 : N
동생의 위치 : K
```

- 동생을 찾는 가장 빠른 시간을 구하는 문제
- 걷기 : X + 1 또는 X -1로 이동 (1초)
- 순간이동 : 2 \* X로 이동 (1초)

정점은 최대 M개 간선은 3M개 `O(M+3M)`

- 순간이동이 존재하지 않는다고 치면 1에서 시작해서 10만까지 가는데 걸리는 시간은 100,000초
- 순간이동이 존재한다면 60,000에서 10만까지 가는 최단시간은 순간이동 -> 20,000번 뒤로오기
- 알 수 있는건 100,000 이상의 수에서 순간이동을 하면 최단시간은 될 수 없다.

```Java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.ArrayDeque;
import java.util.Queue;
import java.util.StringTokenizer;
public class Main {
	static int MAX = 200000;

	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		int N = Integer.parseInt(st.nextToken());
		int K = Integer.parseInt(st.nextToken());
		boolean[] check = new boolean[MAX];
		int[] d = new int[MAX];

		check[N] = true;
		d[N] = 0;

		Queue<Integer> queue =new ArrayDeque<>();
		queue.offer(N);

		while(!queue.isEmpty()) {
			int now = queue.poll();

			if(now - 1 >= 0) {
				if(!check[now-1]) {

				queue.offer(now-1);
				check[now-1] = true;
				d[now-1] = d[now] + 1;
				}
			}

			if(now + 1 < MAX) {
				if(!check[now+1]) {

				queue.offer(now+1);
				check[now+1] = true;
				d[now+1] = d[now] + 1;
				}
			}

			if(now * 2 < MAX) {
				if(!check[now*2]) {

					queue.offer(now*2);
					check[now*2] = true;
					d[now*2] = d[now] + 1;
				}
			}
		}
		System.out.println(d[K]);

	}
}

```
