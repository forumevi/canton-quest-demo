# 🏆 Canton Quest: NFT Badge Collector

> Win **Discord roles** by completing on-ledger quests on **Canton Network** using Daml!

This demo shows how to:
- Issue **NFT-like badges** as Daml contracts
- Link them to **Discord user IDs**
- Verify ownership via **JSON Ledger API**
- (Future) Claim Discord roles automatically

✅ **Live Demo**: `http://136.113.114.56:7575`  
✅ **GitHub**: [Source code](https://github.com/forumevi/canton-quest-demo)

---

## 🚀 How It Works

1. A `Badge` contract is defined in Daml (`QuestBadge.daml`)
2. Canton Sandbox runs on port `6865`
3. JSON Ledger API exposes `/v1/query` on port `7575`
4. External clients can query ledger state with a valid JWT token
5. All components run on a Google Cloud e2-small VM (2 GB RAM)

---

## 🧪 Test the API

### Query all badges (empty ledger):
```bash
curl -X POST http://136.113.114.56:7575/v1/query \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <VALID_JWT_TOKEN>" \
  -d '{"templateIds": ["569d4ee8c16fa3580f1e8b71c1c8b3adb8d6fb57073111d93d34f5d01be42cdb:QuestBadge:Badge"]}'
💡 Replace `<VALID_JWT_TOKEN>` with a token containing:
- `ledgerId: "sandbox"`
- `actAs: ["User1"]`
- `applicationId: "canton-quest-demo"`

✅ Response: `{"result":[],"status":200}`

---

## 📦 Project Structure
canton-quest-demo/
├── daml/
│ └── QuestBadge.daml # NFT badge contract
├── daml.yaml # Daml project config
├── sandbox.log # Canton Sandbox logs
└── json-api.log # JSON API logs

---

## 🛠️ Built With

- **Daml SDK 2.10.2**
- **Canton Sandbox**
- **Google Cloud Platform (e2-small VM)**
- **JSON Ledger API**

---

## 🎁 Why This Matters

- Real on-ledger NFTs (not just frontend!)
- Designed for **community reward systems**
- Fully open-source & reproducible
- Works **7/24 on cloud infrastructure**

Made with ❤️ for the **Canton Developer Quest**!
