# Meningkatkan Retensi Pelanggan dengan Memprediksi Customer Churn 📉📱
By JCDS2602 - Alpha Team (Abe, Alfi, and Hans)

Tableau Link: https://public.tableau.com/shared/DXG5TMGCS?:display_count=n&:origin=viz_share_link

![Screenshot](https://github.com/PurwadhikaDev/AlphaGroup_JC_DS_FT_BSD_26_FinalProject/blob/main/Assets/dash1.jpg)
![Screenshot](https://github.com/PurwadhikaDev/AlphaGroup_JC_DS_FT_BSD_26_FinalProject/blob/main/Assets/dash2.jpg)
![Screenshot](https://github.com/PurwadhikaDev/AlphaGroup_JC_DS_FT_BSD_26_FinalProject/blob/main/Assets/dash3.jpg)


Streamlit Link: https://finpro-telco-churn.streamlit.app/

—-

# 📉 Telco Customer Churn Prediction – Alpha Team

## 1. Ringkasan Proyek
Proyek ini bertujuan untuk **menganalisis data pelanggan perusahaan telekomunikasi** guna memprediksi kemungkinan pelanggan berhenti berlangganan (*churn*). Dengan memanfaatkan **machine learning**, perusahaan dapat **meningkatkan strategi retensi** dan **mengurangi kehilangan pendapatan** akibat churn.  

Pendekatan ini berfokus pada **strategi proaktif**, dengan mengidentifikasi pelanggan berisiko tinggi sejak dini sehingga intervensi (retention offer) bisa dilakukan lebih efisien dibandingkan biaya akuisisi pelanggan baru.

### Tujuan Utama:
- 🎯 **Tujuan 1:** Mengidentifikasi faktor-faktor utama yang menyebabkan churn melalui eksplorasi data dan analisis feature importance.  
- 🧠 **Tujuan 2:** Membangun dan mengoptimalkan model klasifikasi untuk memprediksi churn pelanggan.  
- 💰 **Tujuan 3:** Mengestimasi dampak finansial dari churn (CAC $694 vs CRC $139) dan menekankan recall melalui **F2-Score**.  
- 📊 **Tujuan 4:** Menyediakan rekomendasi strategis yang dapat diimplementasikan oleh tim pemasaran dan manajemen pelanggan.  

---

## 2. Sumber Data
**Telco Customer Churn Dataset**  

- Berisi informasi pelanggan seperti jenis kontrak, layanan tambahan, metode pembayaran, lama berlangganan, biaya bulanan, total tagihan, dan status churn.  
- Dataset setelah filtering: **6.799 pelanggan**.  
- Sumber: [Kaggle - Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/)

---

## 3. Teknologi yang Digunakan
- **Bahasa Pemrograman:** Python (Pandas, NumPy, Scikit-learn, Imbalanced-learn)  
- **Visualisasi:** Matplotlib, Seaborn  
- **Modeling:** Logistic Regression, Random Forest, SVM, KNN, XGBoost, LightGBM, CatBoost, Ensemble (Voting, Bagging, Boosting, Stacking)  
- **Interpretabilitas:** SHAP, LIME  
- **Lingkungan Kerja:** Jupyter Notebook  
- **Deployment:** Model disimpan dalam format `.sav`, `.pkl`, `.pkl (cloudpickle)`  
- **Versi Kontrol:** Git  

---

## 4. Struktur Proyek
- **Assets/** → Gambar visualisasi & ilustrasi model (Decision Tree, RF, SVM, dll)  
- **Data/** → Dataset asli & hasil pembersihan (Telco Churn)  
- **Model/** → Model terlatih (.sav, .pkl, cloudpickle)  
- **Notebook/** → Notebook eksplorasi, EDA, dan training model  
- **telco_churn_app.py** → Aplikasi Streamlit untuk deployment prediksi churn  
- **requirements.txt** → Daftar dependensi Python (yang di luar untuk streamlit, yang di dalam notebook untuk notebook) 
- **convert_to_cloudpickle.py** → Script konversi model ke cloudpickle  
- **README.md**


---

## 5. Ringkasan Temuan

### 5.1 Insight Bisnis
**Faktor Utama Churn:**
- **Jenis kontrak bulanan** → churn rate **42,7%** (vs yearly 11,5%, 2-year 3,1%).  
- **Fiber optic users** → churn tinggi (**41,9%**).  
- **Tanpa layanan tambahan (Online Security, Backup, Tech Support)** → churn > **40%**.  
- **Metode pembayaran electronic check** → churn rate tertinggi (**45,5%**).  
- **Pelanggan senior citizen** → churn rate **41,8%**.  
- **Tenure rendah (<12 bulan)** → segmen paling rawan churn.  

**Segmentasi Risiko Tinggi:**
- Kontrak bulanan + tenure < 12 bulan.  
- Biaya bulanan tinggi (≥ $70) dengan total pembayaran masih rendah (< $2000).  
- Pelanggan tanpa pasangan/tanggungan.  

---

### 5.2 Rekomendasi Strategis
🛠️ **Strategi Operasional**
- Prioritaskan intervensi pada segmen risiko tinggi (email, promo eksklusif, telemarketing).  
- Tawarkan kontrak jangka panjang dengan diskon, bundling, atau loyalty bonus.  

📈 **Optimalisasi Pemasaran**
- Promo onboarding untuk pelanggan baru (< 6 bulan).  
- Edukasi manfaat layanan tambahan (security, backup, tech support) untuk meningkatkan retensi.  

📊 **Integrasi Sistem**
- Integrasikan model prediktif ke CRM → alert otomatis jika risiko churn > **70%**.  
- Gunakan skor churn sebagai dasar pengambilan keputusan tim CS dan retention.  

---

## 6. Keterbatasan Model
- Tidak semua fitur penting tersedia (contoh: interaksi dengan customer service, feedback kepuasan).  
- Outlier dan imbalance data masih memengaruhi performa model meski sudah dilakukan SMOTE.  
- Model belum diuji di lingkungan produksi nyata (real-time scoring + deployment).  
