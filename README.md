# dmip
decentralized metaverse interoperability protocol
```javascript
/*
0. Identity (DMID)
Unique 256/512 bit (32/64 bytes)
*/
const sk = randombytes()
const id = hash(sk.pubkey())
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
const ok = await dmip.send(msg,ids)
```
```javascript
/*
2. Storage API
*/
dmip.setStorageProvider(provider)
const {obj,err} = await dmip.get(id)
const {err} = await dmip.put(obj)
```
```javascript
/*
3. Payments API
*/
dmip.setPaymentsProvider(provider)
const {balance,err} = await dmip.balanceOf(id)
const {err} = await dmip.transfer(id,value)
```
```javascript
/*
4. Tokens API
*/
dmip.setContractsProvider(provider)
const {contract,err} = await dmip.contract(address,abi)
const {err} = await dmip.owner(id,value)
```

```javascript
/*
5. DAO API
*/
dmip.setContractsProvider(provider)
```

