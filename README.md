# dmip
decentralized metaverse interoperability protocol
```javascript
/*
0. Decentralized metaverse identity (DMID)
Unique 256/512 bit (32/64 bytes)
*/
const sk = randombytes()
const id = hash(sk.pubkey())
```
```javascript
/*
1. Decentralized metaverse message API
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
2. Decentralized metaverse storage API
*/
dmip.setStorageProvider(provider)
const {obj,err} = await dmip.get(id)
const {err} = await dmip.put(obj)
```
```javascript
/*
3. Decentralized metaverse payments API
*/
dmip.setPaymentsProvider(provider)
const {balance,err} = await dmip.balanceOf(id)
const {err} = await dmip.transfer(id,value)
```
```javascript
/*
4. Decentralized metaverse tokens API
*/
dmip.setContractsProvider(provider)
const {contract,err} = await dmip.contract(address,abi)
const {err} = await dmip.owner(id,value)
```

```javascript
/*
5. Decentralized metaverse DAO API
*/
dmip.setContractsProvider(provider)
```

