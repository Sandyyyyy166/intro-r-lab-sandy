# 03 ML for complex and high dim biomedical data
## Background
> [!NOTE]
> 核心问题Can RNA expression distinguish TP53 variant consequence classes in unseen CCLE cell lines?
> 我们能不能通过 RNA 基因表达数据，预测一个从来没有见过的癌症细胞系属于哪种 TP53 突变后果类别？
- Gene expression（基因表达）：某个基因有多活跃，通常在这里通过 RNA 水平来衡量。
- RNA expression data：告诉我们每个基因对应的 RNA 有多少。
<img width="644" height="212" alt="截屏2026-11-04 09 56 19" src="https://github.com/user-attachments/assets/13d18efc-a5fd-4454-9869-011b0091ed1e" />
<img width="635" height="447" alt="截屏2026-11-04 09 56 38" src="https://github.com/user-attachments/assets/560bf00d-9470-4fbe-bde9-ff0ba9de493b" />
<img width="638" height="424" alt="截屏2026-11-04 09 57 07" src="https://github.com/user-attachments/assets/6ffa4e6e-fc7d-4e38-9441-95cbf4566da1" />

## 为什么要分Training / Validation / Test？
<img width="638" height="554" alt="截屏2026-11-04 09 57 58" src="https://github.com/user-attachments/assets/7a627450-7c0a-4d9e-bdeb-444e08ee3207" />

!!待补充elastic net

## Tree Models & XGBoost
<img width="615" height="555" alt="截屏2026-11-04 10 19 26" src="https://github.com/user-attachments/assets/d66b963f-5e43-44be-a191-2ea78650078d" />
<img width="773" height="377" alt="截屏2026-11-04 10 20 52" src="https://github.com/user-attachments/assets/37650b44-d7cf-47eb-a54a-6c88af09cb74" />

> [!TIP]
> Bagging（Random Forest）：找 100 个同学，每个人独立做题，最后投票决定答案。
> Boosting（XGBoost）：第一个同学先答题，第二个同学根据当前答案的不足进行纠正，第三个继续改进……
> **Decision Tree**：通过不断划分数据来预测类别。
> **Random Forest**：Parallel / Independent（独立建树，再综合）**多棵树分别学习，最后综合结果**。
> **XGBoost**：Sequential / Corrective（顺序建树，不断纠正）**后一棵树根据前面的预测继续改进。**

<img width="745" height="379" alt="截屏2026-11-04 10 25 01" src="https://github.com/user-attachments/assets/80a604f6-2cc6-45e9-8063-4fc85e462888" />
<img width="561" height="515" alt="截屏2026-11-04 10 26 11" src="https://github.com/user-attachments/assets/4b9970a1-b73d-4019-89ab-78e1fa93fb76" />

- A new tree is fitted to directions that would reduce the loss most rapidly.
意思是：
新的一棵树会学习怎样调整当前预测，才能最快地减少错误。
- Loss function（损失函数） = 衡量模型预测有多差的函数。
Loss 越小，代表模型在这个指标下预测得越好。

### Step 1 Define the Objective
<img width="772" height="388" alt="截屏2026-11-04 10 40 07" src="https://github.com/user-attachments/assets/8575eb01-da87-4c12-9ac0-710cba393e1c" />
<img width="438" height="551" alt="截屏2026-11-04 10 40 35" src="https://github.com/user-attachments/assets/91336326-8dad-447f-a63c-f6a509e1b79d" />
<img width="622" height="522" alt="截屏2026-11-04 10 40 47" src="https://github.com/user-attachments/assets/534a1ebc-ac70-4064-be53-562076c8d18e" />
<img width="430" height="429" alt="截屏2026-11-04 10 40 59" src="https://github.com/user-attachments/assets/ed498963-87d2-4af8-b24f-6396bc841155" />

### Step 2 Initialise Predictions
<img width="701" height="243" alt="截屏2026-11-04 10 41 55" src="https://github.com/user-attachments/assets/6f342dcb-1d4d-4ddb-b4fa-d3e0af258672" />
<img width="368" height="590" alt="截屏2026-11-04 10 42 14" src="https://github.com/user-attachments/assets/044328be-379d-4dd0-b0c0-099fd7d2f8ea" />
<img width="632" height="586" alt="截屏2026-11-04 10 44 59" src="https://github.com/user-attachments/assets/1ec67a5f-c286-4c6f-b7c8-3f0a603670c0" />
<img width="615" height="498" alt="截屏2026-11-04 10 42 26" src="https://github.com/user-attachments/assets/77f9469f-fde8-4643-8a9e-a03c54272bd2" />



### Step 3 Calculate Gradients and Curvature
<img width="771" height="418" alt="截屏2026-11-04 10 43 26" src="https://github.com/user-attachments/assets/89c1d2f6-65ec-4534-ae76-7159f3b375dc" />
<img width="418" height="603" alt="截屏2026-11-04 10 49 19" src="https://github.com/user-attachments/assets/ae6837b9-6336-4116-a2e4-f6232edd4bed" />
<img width="627" height="667" alt="截屏2026-11-04 10 49 31" src="https://github.com/user-attachments/assets/b8f2cf6d-3def-455f-b249-3e9ec19cba41" />
<img width="612" height="523" alt="截屏2026-11-04 10 49 45" src="https://github.com/user-attachments/assets/c747dd9b-8b4b-46b5-b765-528f8a73e6da" />

> [!TIP]
> Gradient 为负不是说模型表现不好，而是说增加当前 Raw Score 可以让 Loss 下降。

<img width="424" height="382" alt="截屏2026-11-04 10 46 18" src="https://github.com/user-attachments/assets/e89f6efa-3775-4256-a6dd-f9b9d31b0a60" />
<img width="592" height="547" alt="截屏2026-11-04 10 46 39" src="https://github.com/user-attachments/assets/ecc1dc32-eebb-4448-afff-87d49681a2e5" />
<img width="615" height="539" alt="截屏2026-11-04 10 47 20" src="https://github.com/user-attachments/assets/98c4b882-436f-42dc-a663-b1c99d494692" />
<img width="614" height="281" alt="截屏2026-11-04 10 47 47" src="https://github.com/user-attachments/assets/71073c21-18ca-4183-957b-284ab25b4778" />

!!待补充其他step

### 总结：XGBoost
<img width="773" height="355" alt="截屏2026-11-04 11 19 03" src="https://github.com/user-attachments/assets/304930d1-2436-4ade-a6b0-4fe20937a1ae" />
<img width="609" height="514" alt="截屏2026-11-04 11 20 25" src="https://github.com/user-attachments/assets/91e3c03a-411f-4f2a-9ade-c5f93e0b4a05" />
<img width="594" height="525" alt="截屏2026-11-04 11 21 06" src="https://github.com/user-attachments/assets/8145c440-47d5-4957-a379-9213c04d3b41" />

## Practical: CCLE data
<img width="358" height="333" alt="截屏2026-11-04 11 53 41" src="https://github.com/user-attachments/assets/f0899c80-4e15-477d-928c-dce4a6e3d7b8" />
<img width="634" height="590" alt="截屏2026-11-04 11 25 31" src="https://github.com/user-attachments/assets/a4b7a8e1-44d8-4288-b1c9-51d1de29ec56" />
<img width="621" height="480" alt="截屏2026-11-04 11 26 47" src="https://github.com/user-attachments/assets/79cdecd9-65cc-4545-8d10-d1dba447a49a" />
<img width="759" height="340" alt="截屏2026-11-04 11 27 55" src="https://github.com/user-attachments/assets/66c3b8f2-e88a-4183-b489-71083621096b" />

### Why join?
<img width="740" height="413" alt="截屏2026-11-04 11 27 30" src="https://github.com/user-attachments/assets/02421db0-c1ff-4d3f-b53d-7c437e1a245f" />
<img width="618" height="581" alt="截屏2026-11-04 11 28 12" src="https://github.com/user-attachments/assets/9f01e82b-0b9e-4d56-971c-cda7c5ab7f83" />

### What are we predicting?
<img width="776" height="377" alt="截屏2026-11-04 11 31 56" src="https://github.com/user-attachments/assets/356bc15e-e0d1-4cba-9b3d-93bf7dff6aa8" />
<img width="557" height="493" alt="截屏2026-11-04 11 32 09" src="https://github.com/user-attachments/assets/240e6dc6-56e1-45b5-81d8-a447e4fb7c36" />

!!待补充46-49
### From Prediction to Regulatory Explanation

### Gene Regulatory Networks 生物学网络和优化思想
- Gene Regulatory Network = 基因调控网络。
- Node = Gene（基因）
- Edge = Interaction（相互作用）
<img width="626" height="477" alt="截屏2026-11-04 11 39 16" src="https://github.com/user-attachments/assets/ec0a84cd-3507-4c3e-b09a-8c0c907dbae6" />
<img width="504" height="405" alt="截屏2026-11-04 11 40 42" src="https://github.com/user-attachments/assets/5aec9535-6239-496a-ae12-15fbb787284f" />
<img width="592" height="616" alt="截屏2026-11-04 11 40 28" src="https://github.com/user-attachments/assets/b9beb745-84cb-4706-8ef6-adb7d139f1be" />
<img width="721" height="354" alt="截屏2026-11-04 11 46 06" src="https://github.com/user-attachments/assets/1ef28167-ba1c-4e33-9278-8ec5c104c699" />
<img width="540" height="573" alt="截屏2026-11-04 11 46 24" src="https://github.com/user-attachments/assets/b3085702-2928-47f7-9263-bf4edb10d5cc" />
<img width="560" height="240" alt="截屏2026-11-04 11 46 39" src="https://github.com/user-attachments/assets/e233f69b-0757-47e2-b3a4-20ac031f9a6b" />
<img width="613" height="664" alt="截屏2026-11-04 11 47 24" src="https://github.com/user-attachments/assets/d5bad0d6-785f-4829-9dac-0d1cc31e2d09" />

### CARNIVAL
<img width="582" height="680" alt="截屏2026-11-04 11 48 00" src="https://github.com/user-attachments/assets/64094d5f-df25-4c9f-8b7d-752d0ed10423" />
<img width="766" height="400" alt="截屏2026-11-04 11 49 18" src="https://github.com/user-attachments/assets/6367d761-24c8-424a-94bc-1f4a980231cb" />
<img width="752" height="422" alt="截屏2026-11-04 11 49 35" src="https://github.com/user-attachments/assets/3b3f32ee-d4db-4887-ad8e-b6895498daf2" />
<img width="573" height="491" alt="截屏2026-11-04 11 50 07" src="https://github.com/user-attachments/assets/b3fd53de-3320-4a2a-a3cc-7e98a3afad4f" />
<img width="613" height="579" alt="截屏2026-11-04 11 50 29" src="https://github.com/user-attachments/assets/949c0147-3938-4f00-9ef5-cdd3e6228b5a" />

## Combining models
<img width="768" height="372" alt="截屏2026-11-04 11 52 15" src="https://github.com/user-attachments/assets/9daa5516-eb95-4ede-9aad-95465eb2e2b1" />
<img width="772" height="376" alt="截屏2026-11-04 11 55 30" src="https://github.com/user-attachments/assets/e6f5542e-422a-44c3-8cbd-390316ec6979" />

> [!TIP]
> 


