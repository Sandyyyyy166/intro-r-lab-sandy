# 01 为什么做健康数据分析之前，我们必须先弄清楚数据代表什么、如何整理、是否可靠，以及能不能用于建模？
## 1 Health Data Foundation
<img width="674" height="314" alt="截屏2026-11-02 09 17 22" src="https://github.com/user-attachments/assets/bf0bd7f4-29ad-4cb0-bd67-3efbea65006f" />
<img width="655" height="289" alt="截屏2026-11-02 09 21 25" src="https://github.com/user-attachments/assets/966a117a-289a-44e1-8b73-928b6647a2aa" />
<img width="647" height="332" alt="截屏2026-11-02 09 21 39" src="https://github.com/user-attachments/assets/cc844f57-bd21-47cd-904c-dac091140c84" />

### Structured, semi structured and unstructured data
<img width="668" height="300" alt="截屏2026-11-02 09 28 48" src="https://github.com/user-attachments/assets/06c33f53-025b-4c65-83d7-dd8aac1bf714" />

### 为什么我们需要这些technicals
<img width="699" height="348" alt="截屏2026-11-02 09 33 33" src="https://github.com/user-attachments/assets/359cb485-4759-41e5-9ce8-e4a392c7ec13" />

### Phenotype & Computable phenotype
- Phenotype: 你实际表现出了什么特征(身高、血压、血糖水平、某些疾病表现)
- Computable phenotype = 把一个医学概念转化成计算机能够执行的判断规则。
<img width="672" height="151" alt="截屏2026-11-02 09 36 50" src="https://github.com/user-attachments/assets/8f70777c-9d7d-4ff4-8a37-ef77cc7a2473" />
<img width="1336" height="628" alt="image" src="https://github.com/user-attachments/assets/9acd6e17-721e-4bbd-8eac-8d4d8809ece4" />
<img width="671" height="244" alt="截屏2026-11-02 09 42 28" src="https://github.com/user-attachments/assets/84d17d82-dabf-4c62-aca7-d0340a601b8e" />
<img width="655" height="474" alt="截屏2026-11-02 09 43 05" src="https://github.com/user-attachments/assets/dbfb8f93-34aa-4468-be16-1c36994e9f37" />
<img width="582" height="487" alt="截屏2026-11-02 09 44 00" src="https://github.com/user-attachments/assets/5b038ecc-401b-460b-a8b5-3af97fd12424" />
<img width="448" height="341" alt="截屏2026-11-02 09 44 30" src="https://github.com/user-attachments/assets/02813de6-48ab-478e-9ab4-e5c1778b168b" />
<img width="681" height="665" alt="截屏2026-11-02 09 44 55" src="https://github.com/user-attachments/assets/082bcdd1-1179-4c81-b64f-d91b7e2d90a2" />

## 2 Data Structure and Integration 怎样把原始数据整理成分析表？
<img width="568" height="440" alt="截屏2026-11-02 09 53 07" src="https://github.com/user-attachments/assets/a319fd45-3e2d-4ecc-8b1a-0099f3790216" />
<img width="653" height="527" alt="截屏2026-11-02 09 53 18" src="https://github.com/user-attachments/assets/7e4a816e-a36f-4d0d-bec0-e14bf4b5e1f4" />

### Unit of analysis
- Unit of analysis（分析单位）：你想对谁得出结论。决定你的研究结论针对什么对象.
- Unit of observation（观测单位）：一条观测记录对应什么。
- 比如我们想预测：
“这个肝脏最终属于哪个风险等级？”
那么研究结论针对的是 liver。
所以：
Unit of analysis = liver。
- 数据表的行数不等于独立研究对象的数量。

### Identifier ???
- 现在我们知道一份数据里可能有很多重复测量。
下一个问题是：
计算机怎么知道哪些记录来自同一个肝脏？
答案是：**Identifiers（标识符）**。
<img width="688" height="454" alt="截屏2026-11-02 09 59 18" src="https://github.com/user-attachments/assets/65bacac9-1b3e-46ee-ae9f-40b01d480506" />
<img width="699" height="658" alt="截屏2026-11-02 09 59 50" src="https://github.com/user-attachments/assets/2126cf28-94aa-4ce2-9205-137938efeba3" />

### Data provenance 数据溯源+记录过程
<img width="694" height="547" alt="截屏2026-11-02 10 17 30" src="https://github.com/user-attachments/assets/3ac0ff7a-f41a-46b3-8e1c-9678d5e2b94b" />

### FAIR：为什么数据还需要管理原则？
<img width="538" height="561" alt="截屏2026-11-02 10 20 05" src="https://github.com/user-attachments/assets/3a050247-98d9-44aa-8868-7f0e8dd18372" />

## 3 Data Cleaning and EDA 有表格了-先理解和检查数据-再做机器学习
### Median、IQR 和 Outliers
<img width="630" height="297" alt="截屏2026-11-02 10 29 11" src="https://github.com/user-attachments/assets/af2d5ed0-d6ac-41a6-8de5-e3945be7c4f5" />
<img width="412" height="348" alt="截屏2026-11-02 10 28 46" src="https://github.com/user-attachments/assets/1ca6c634-092f-48e0-af3b-bfc783209d40" />
<img width="510" height="293" alt="截屏2026-11-02 10 29 46" src="https://github.com/user-attachments/assets/327951ad-32da-497a-a92a-e7458b999e08" />

### Log transformation
<img width="681" height="647" alt="截屏2026-11-02 10 30 44" src="https://github.com/user-attachments/assets/0223f756-4ebc-4ba1-a50d-f3a4eefe5852" />

- Log transformation 可以降低右偏程度，让数据更容易分析。
- 但不是所有变量都需要 log transformation，而且不能对不符合变换定义域的数值直接使用这个公式。
<img width="619" height="434" alt="截屏2026-11-02 10 32 21" src="https://github.com/user-attachments/assets/c8c60e55-b849-46f5-bb5f-b92ff271868b" />

### Empirical Cumulative Distribution Function ECDF（经验累积分布函数）
<img width="769" height="425" alt="截屏2026-11-02 10 34 06" src="https://github.com/user-attachments/assets/87513a59-4ac2-4fea-bf5c-37d28a5c2d68" />
<img width="672" height="670" alt="截屏2026-11-02 10 33 46" src="https://github.com/user-attachments/assets/d8c1c037-bb83-46fc-9ab3-60fc022ac313" />

### Missing value ???
<img width="369" height="686" alt="截屏2026-11-02 10 36 38" src="https://github.com/user-attachments/assets/e46563c5-6b4a-4897-8bd5-140f628b7f17" />
<img width="574" height="218" alt="截屏2026-11-02 10 37 04" src="https://github.com/user-attachments/assets/bc26e8dc-21ca-43b4-ae98-6234798f7cf4" />

- 不能直接删除NA：可能会删除strong signal（比如病情最严重的群体）, 造成 selection bias。
- Handling missing data -> Imputation
<img width="672" height="336" alt="截屏2026-11-02 10 39 21" src="https://github.com/user-attachments/assets/843e6b95-06f3-4715-afd0-d14a91b49116" />

- Imputation Tools
<img width="767" height="423" alt="截屏2026-11-02 10 40 28" src="https://github.com/user-attachments/assets/73b6dae3-37a1-44e0-99e8-7784f20bfff1" />
<img width="526" height="623" alt="截屏2026-11-02 10 41 12" src="https://github.com/user-attachments/assets/513d8984-1acb-48ec-b332-1ff2cb5cfa1b" />

### Scaling and KNN ？？？
假设你想找出与 Liver A 最相似的其他肝脏。
我们有两个变量：Lactate 和 LDH。
Lactate 的值可能在 1–5 左右。
LDH 的值可能在几百左右。
如果直接计算距离，LDH 的数值差异可能远大于 lactate 的数值差异。
于是 LDH 可能主导“谁更相似”的判断。

<img width="508" height="485" alt="截屏2026-11-02 10 43 39" src="https://github.com/user-attachments/assets/a82609da-1fa9-478f-8490-ccbf7d9b4214" />
<img width="677" height="436" alt="截屏2026-11-02 10 44 17" src="https://github.com/user-attachments/assets/880aa00e-fb52-4b9e-a6d0-a988500172f4" />
<img width="659" height="428" alt="截屏2026-11-02 10 44 39" src="https://github.com/user-attachments/assets/f71d7bdd-3728-41dc-9065-3ad4116aa60e" />

- **Scaling → Calculate distance → Find neighbours → Impute missing value** ？？？
<img width="774" height="430" alt="截屏2026-11-02 10 48 03" src="https://github.com/user-attachments/assets/a1cb751d-73cb-46c7-8ddc-db15bfc70b55" />
<img width="466" height="400" alt="截屏2026-11-02 10 48 17" src="https://github.com/user-attachments/assets/de41f186-859a-428c-93d6-13ff481a5ad8" />

### Bivariate visualisation
<img width="768" height="245" alt="截屏2026-11-02 10 51 00" src="https://github.com/user-attachments/assets/ca2c65bb-2c88-43af-bd1b-33e5209f13ef" />
<img width="772" height="419" alt="截屏2026-11-02 10 51 10" src="https://github.com/user-attachments/assets/dfea1156-c295-4f82-b01b-d22b699bb626" />

### Pearson and Spearman correlation
- *Pearson correlation*
- Pearson 衡量两个变量的线性相关程度。
- 相关系数 \(r\) 的范围是：
\[
-1\leq r\leq1
\]
- r 接近 +1：强正线性相关。
- r 接近 -1：强负线性相关。
- r 接近 0：线性相关较弱。
- *Spearman correlation*
- Spearman 使用变量的排序信息来衡量单调关系。
- 例如：
随着 X 增加，Y 也持续增加，但它们不是沿着一条直线变化。
- 这种情况下，Spearman 可能更能反映它们的单调关系。
