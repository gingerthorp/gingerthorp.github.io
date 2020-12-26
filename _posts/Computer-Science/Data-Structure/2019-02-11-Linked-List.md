---
title: List(연결리스트)
date: 2019-02-11 12:00:00 +0900
categories: [Computer-Science, Data-Structure]
tags: [Study]     # TAG names should always be lowercase
toc: False
---

## LIST(연결리스트)

연결리스트는 랜덤 접근이 가능한 배열과는 다른 순차적인(sequential) 자료구조입니다.
연결리스트는 노드들로 구성되어 있습니다. 노드는 저장할 값과 다음 노드를 가리키는 포인터로 이루어져 있습니다. 연결리스트의 첫 노드인 헤드(Head)로 부터 노드에 다음 노드를 가리키는 포인터를 사용해 리스트를 순회할 수 있게 됩니다.

![List(연결리스트)](https://user-images.githubusercontent.com/19174106/52542355-2cdc3a80-2de2-11e9-8687-2fe0d1aad9ce.jpg)

위와 같은 연결리스트를 Singly Linked List라고 합니다.

Singly Linked List의 각 노드에 이전 노드를 가리키는 포인터를 추가하게 되면 양방향으로 순회가 가능한 Doubly Linked List가 되고, 환형 큐(Circular Queue)와 같이 연결리스트의 마지막 노드인 테일(Tail)과 헤드를 이으면 Circular Linked List가 됩니다.
이는 문제의 상황에 따라 구현하여 사용하시면 됩니다.

![Doubly Linked List](https://user-images.githubusercontent.com/19174106/52542439-fce16700-2de2-11e9-941d-04469af3fbdc.jpg)

**각 노드는 저장할 값과 자신의 앞, 뒤 노드를 가르키는 포인터를 가짐**

![Circular Linked List](https://user-images.githubusercontent.com/19174106/52542441-feab2a80-2de2-11e9-8027-6c768f575a96.jpg)

**테일의 포인터는 헤드를 가르킴**

두 자료구조의 장단점을 나열해보자면, 배열은 인덱스로 인한 무작위 접근이 가능하고, 리스트에 비해 저장공간을 적게 필요로 하지만, 리스트에 비해 자료의 삽입, 삭제가 비효율 적인 부분이 있습니다. 순서를 유지하면서 자료를 삽입 / 삭제하기 위해서는 최악의 경우 모든 데이터를 옮겨주어야 하기 때문입니다.

리스트는 무작위 접근이 불가능하므로 무조건 순차적으로 탐색해야 하며, 노드에 저장할 값과 포인터를 포함하고 있기 때문에 똑같은 크기의 배열에 비해 저장공간을 많이 차지하게 되지만, 자료의 삽입과 삭제가 새로운 노드를 만들어 포인터로 이어주기만 하면 되기 때문에 간편하고 유연하게 동작합니다.

![스크린샷 2020-12-26 오전 10 41 48](https://user-images.githubusercontent.com/19174106/103144105-2ac9bd80-4767-11eb-9a93-718c3ceca63a.png)

리스트와 배열의 시간복잡도 비교,https://en.wikipedia.org/wiki/Linked_list

