# how to resolve git conflict - basic

## Scenario

คุณกำลังโปรเจคเปลี่ยนโลกกับเพื่อนๆอยู่ แต่ว่าเพื่อนแอบเพิ่มไฟล์สุด `เจ๋ง` เข้าไปในโปรเจคของคุณ คุณพยายามจะ push ไฟล์ของคุณขึ้นไปแต่เพื่อนของคุณก็พยายาม push ไฟล์ของเขาขึ้นไปด้วย จนทำให้เกิด conflict ขึ้นคุณจะทำอย่างไร?

### Divergent Push

#### Setup

**Person 1**

File: `p1_file.txt`
```bash
echo "Hi, I am P1. I want to add some cool stuff!" >> p1_file.txt
```

**Person 2**

File: `p2_file.txt`
```bash
echo "Hi, I am P2. I want to add some cool stuff too!" >> p2_file.txt
```

#### Steps

1. **Person 1** ทำการ push ไฟล์ของตัวเองขึ้นไป
```bash
git add p1_file.txt
git commit -m "p1 add cool stuff!"
git push origin main
```

2. **Person 2** ทำการ push ไฟล์ของตัวเองขึ้นไป
```bash
git add p2_file.txt
git commit -m "p2 add cool stuff!"
git push origin main

```

> [!Note]
> **Person 2** จะพบ conflict ขึ้นหลังจากทำการ push ไฟล์ของตัวเองขึ้นไป
