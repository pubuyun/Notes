## TODO:

``` CSharp
// CLIENT
using UnityEngine;
using UnityEngine.Networking;

public class CardClient : NetworkBehaviour
{
    public Transform handTransform; // 玩家手牌栏的Transform
    private CardServer cardServer;

    void Start()
    {
        cardServer = FindObjectOfType<CardServer>();
    }

    [Command]
    public void CmdDrawCard()
    {
        int cardIndex = cardServer.DrawCard();
        if (cardIndex != -1)
        {
            RpcReceiveCard(cardIndex);
        }
    }

    [ClientRpc]
    void RpcReceiveCard(int cardIndex)
    {
        GameObject cardPrefab = cardServer.cardPrefabs[cardIndex];
        GameObject drawnCard = Instantiate(cardPrefab);
        drawnCard.transform.SetParent(handTransform, false);
    }
}
```

``` Csharp
// SERVER
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.Networking;

public class CardServer : NetworkBehaviour
{
    public List<GameObject> cardPrefabs; // 存储所有卡牌Prefab的列表
    private List<int> deck = new List<int>(); // 卡牌堆，存储卡牌Prefab的索引

    void Start()
    {
        // 初始化卡牌堆
        for (int i = 0; i < cardPrefabs.Count; i++)
        {
            deck.Add(i);
        }
    }

    [Server]
    public int DrawCard()
    {
        if (deck.Count > 0)
        {
            int randomIndex = Random.Range(0, deck.Count);
            int cardIndex = deck[randomIndex];
            deck.RemoveAt(randomIndex);
            return cardIndex;
        }
        else
        {
            Debug.Log("卡牌堆已空！");
            return -1; // 表示没有卡牌了
        }
    }
}
```
1. **CardClient**:
    - **handTransform**: 玩家手牌栏的Transform。
    - **CmdDrawCard()**: 客户端请求服务器抽取一张卡牌。
    - **RpcReceiveCard(int cardIndex)**: 客户端接收服务器发送的卡牌，并将其实例化到玩家手牌栏。
2. **CardServer**:
    - **cardPrefabs**: 存储所有卡牌Prefab的列表。
    - **deck**: 卡牌堆，存储卡牌Prefab的索引a。
    - **DrawCard()**: 从卡牌堆中随机抽取一张卡牌，并返回其索引。