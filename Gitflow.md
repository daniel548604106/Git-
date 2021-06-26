
## Git Flow 分支介紹

長期分支

- master: 主分支
- develop: 開發分支

任務分支

- feature: 新功能分支
- release: 發佈分支
- hotfix: 熱修復分支


### master 分支

git 專案初始化時的預設分支，在 git flow 中被定義為穩定的線上版本，主要的任務是紀錄與追蹤正式釋出的版本狀態，因此 tag 的版本號也會紀錄在此分支的 commit 上。

### develop 分支

來源從 master 的最初提交開始，在 git flow 中被定義為主要開發分支該分支作為所有開發的基礎，由此擴增新功能，也由此進行新版本的發佈。

### feature分支

- develop ⇒ feature ⇒ develop

來源從 develop 分支開始，在 git flow 中被定義為新功能分支
該分支作為 develop 的子項任務分支，從 develop 開始，發展在 feature ，最終結束於 develop feature 分支依據任務的不同，在同一時間可能會多組進行，而 feature 中的子項任務
同樣歸類於 feature 分支。

### release 分支

- develop  ⇒ release  ⇒ master / develop

來源從 develop 分支開始，在 git flow 中被定義為發佈分支，
該分支作為`上線前的測試分支`，會在 release 分支上進行最終測試。

測試時，若發現有問題則在此分支上立即修復，當驗證一切功能正常後，除了合併到 master 分支作為正式版本發佈外，
還會合併到 develop 分支，同步修正的程式。

### hotfix 分支

- master  ⇒ hotfix ⇒ master / develop

來源從 master 分支開始，在 git flow 中被定義為熱修復分支，
該分支作為線上產品發生問題時緊急修復的分支，會從紀錄正式版本的 master 分支切出，
待 hotfix 的修復任務完成後，除了合併回 master 分支，也會合併到 develop 分支，同步修正的程式。
