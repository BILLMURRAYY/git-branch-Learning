# git-branch
START
-------------------------------------------
git config --global user.name "John Doe" <br>
git config --global user.email johndoe@example.com <br>
<br>
git config --list <br>
git config --global --list <br>

Day1
การใช้งาน Git Step by Step
-------------------------------------------
1. การสร้าง git ลงในโปรเจ็กต์
---
git init

2. เปิดโปรเจ็กต์เข้า VS Code
---
code .

3. สร้างไฟล์ต่างๆ ในโปรเจ็กต์ของเรา
---
.git
src
   |-- coding.txt
greeting.txt

4. เรียกดูสถานะไฟล์
---
git status

5. ทำการ trackfile เข้าสู่ staging area
---
git add greeting.txt
git add .
git add src/*.txt

6. การลบออกจาก staging area
---
git reset greeting.txt
git reset folder_name

7. การบันทึกประวัติการทำงาน (code)
---
git commit -m "first commit"

8. เรียกประวัติที่บันทึกไว้
---
git log

9. หากต้องการลบ commit ออก
---
git update-ref -d HEAD

10. การย้อนประวัติด้วย git checkout
---
git checkout 0de0b91

11. การเรียกดูประวัติที่ถูกย้อนข้ามไปแล้ว
---
git reflog

12. หากต้องการย้อนประวัติแบบไม่เก็บของเดิมไว้
---
git reset --hard 0de0b91

Day2
=========================
การทำงานกับ Git Branch

Step 0: เปิดโปรเจ็กต์ที่ต้องการเข้ามาใน VS Code
---
code .

Step 1: Setup git ลงในโปรเจ็กต์
---
git init

Step 2: Track file ในโปรเจ็กต์
---
git add .

Step 3: Commit file ในโปรเจ็กต์
---
git commit -m "first commit"

Step 4: เปลี่ยนชื่อ branch จาก master เป็น main
---
git branch -M main

Step 5: คำสั่งเรียกดู branch ทั้งหมด
---
git branch

Step 6: การสร้าง branch ใหม่
---
git branch dev

Step 7: เปลี่ยนไปทำงานที่ branch dev
---
git checkout dev

เราลอง checkout กลับไปที่ main
---
git checkout main

Step 8: ลองสร้างใหม่ แล้วทำการ checkout ไปที่ branch ที่สร้างทันที
---
git checkout -b feature


Step 9: การรวม branch  ย่อย กลับเข้า branch หลัก
---
git merge feature --no-ff

Step 10: รวม branch เข้า main
---
git merge dev

Steip 11: สร้างไฟล์ .gitignore
---
.gitignore

กรณีสร้างไฟล์ .gitignore ภายหลัง เราจะต้องแก้ปํญหาด้วยคำสั่งดังนี้
---
ก่อนใช้คำสั่งด้านล่างควร commit ให้เรียบร้อยก่อน
git rm -rf --cached .
git add .

Step 12: add remote
---
git remote add origin https://github.com/iamsamitdev/git-br...


หากต้องการเช็คว่า ตัวโปรเจ็กต์เราผูกอยู่ที่ remote ไหน
---
git remote show origin

Step 13: การอัพโหลดโค๊ดขึ้น remote (github) server
---
git push -u origin main

Day3
=========================
การทำงานกับ Github และ Netlify

Step 1: ทำการ init setup git เข้าโปรเจ็กต์<br />
Step 2: Commit<br />
Step 3: Rename branch<br />
Step 4: Add remote (ผูกไปที่ github.com)<br />
Step 5: Push to remote (github.com)<br />
Step 6: Create new branch "dev"<br />
Step 7: Edit souce code<br />
Step 8: Commit<br />

หลังจาก commit ใน branch dev
เราจะสามารถรวม code ได้ 2 วิธีการ
---
1. merge ผ่าน github ด้วย pull request
2. merge บน local และ push ไปที่ github

มาขึ้นโปรเจ็กต์ Next.js กันเถอะๆๆๆ
----
npx create-next-app next-workshop

รันโปรเจ็กต์ next.js
----
npm run dev
