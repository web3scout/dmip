# dmip
decentralized metaverse interoperability protocol
```javascript
/*
0. Identity (DMID)
Unique 256/512 bit (32/64 bytes)
*/
const sk = randombytes()
const id = await hash(sk.pubkey())
```
```javascript
/*
1. Message API
dmip.send(msg,ids)
dmip.onmsg((msg)=>{})
*/
const ids=[id0,id1,id2]
const data={msg:"Hello metaverse!"}
const sigs=[await sk.sign(data)]
const msg = {data,sigs}
await dmip.send(msg,ids)
dmip.onmsg((msg)=>{
 const {data,sigs} = msg;
})
```
```javascript
/*
2. Storage API
*/
const st1=dmip.getStorageAPI(stId1)
const obj = await st1.get(id)
await st1.put({})
```
```javascript
/*
3. Payment API
*/
const p1=dmip.getPaymentAPI(pId1)
const balance = await p1.balanceOf(id)
await p1.transfer(id,value)
```
```javascript
/*
4. Token API
*/
const t1=dmip.getTokenAPI(tId1)
const totalSupply1 = await t1.totalSupply()
await t1.transfer(id,value)

const t2=dmip.getTokenAPI(tId2)
const totalSupply2 = await t2.totalSupply()
await t2.transfer(ownerId,tokenId)
```

```javascript
/*
5. DAO API
*/
const d1=dmip.getDAOAPI(dId1)
const props = await d1.proposals()
```

```javascript
/*
5. Contract API
*/
const capi1=dmip.getContractAPI(cId1)
const c1 = await capi1.deploy()
```

