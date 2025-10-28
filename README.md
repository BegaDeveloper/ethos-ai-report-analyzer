# 📊 AI Report Analyzer | Ethos (Switzerland)

## 🚀 Introduction

**Ethos – AI Report Analyzer** is a **Swiss financial analytics platform** that enables companies to upload, search, and analyze large-scale PDF and document datasets.
Built around advanced AI capabilities, the system automatically **extracts insights**, **highlights key information**, and **annotates relevant sections directly within the PDF** when users perform searches or analyses.

The goal of Ethos is to help financial analysts, auditors, and compliance officers **quickly identify critical data points** across hundreds of pages of reports — turning static financial documents into **interactive, intelligent knowledge sources**.

---

## 🧠 What the App Does

Ethos allows users to interact with their financial documents in real time.
Once a company uploads its reports, the system processes the content through an AI backend that performs semantic search, entity recognition, and contextual annotation.

Core functionality includes:

* 📂 **PDF Upload & Processing** – Upload annual reports, financial statements, or audit files.
* 🤖 **AI Extraction** – Identify relevant text segments, keywords, and financial entities automatically.
* 🖊️ **PDF Annotation Engine** – Display AI insights directly on the document using canvas overlays.
* 🔍 **Semantic Search** – Find data points and see highlighted matches instantly within the file.
* 📊 **Data Visualization** – Render extracted metrics and insights through interactive D3.js charts.

---

## 🧩 Technologies Used

| Layer               | Stack / Tools                                                          | Description                                                                          |
| ------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Frontend**        | **Angular 18**, **RxJS**, **NgRx**, **Fabric.js**, **D3.js**, **SCSS** | Built the entire UI layer with dynamic PDF rendering, annotation, and visualization. |
| **Backend / Cloud** | **Firebase (Auth + Firestore + Storage)**                              | Managed authentication, document storage, and AI-result persistence.                 |
| **AI Integration**  | **Custom REST API (via Express)**                                      | Provided AI-generated highlights and extraction data.                                |
| **Deployment**      | **Firebase Hosting / Cloud Functions**                                 | Served SPA with serverless APIs for annotation and indexing.                         |

---

## 💻 My Role & Contributions

I worked as a **solo Frontend Developer** responsible for architecting and implementing the entire Angular application from the ground up.
My responsibilities included UI/UX design, component architecture, real-time data visualization, and AI annotation rendering.

Key contributions:

* Designed and built the **full Angular 18 application** architecture using a modular, scalable approach.
* Integrated **Firebase Auth & Firestore** for secure data management and live updates.
* Implemented a **custom Fabric.js canvas layer** for dynamic, AI-driven PDF annotations.
* Developed **interactive visualizations** using **D3.js** to represent extracted financial metrics.
* Created a **PDF viewer component** supporting zoom, pan, annotation layers, and highlight overlays.
* Collaborated with AI engineers to ensure frontend compatibility with extraction APIs and JSON annotation structures.

---

## ⚙️ Key Technical Highlights I Implemented

### 🧩 1. AI-Driven PDF Annotation Engine (Fabric.js)

The core challenge was rendering AI-detected insights directly on top of complex, multi-page PDFs without performance loss.

I built a **custom annotation engine** using **Fabric.js**, where each PDF page acts as a canvas layer:

```typescript
const canvas = new fabric.Canvas('pdf-canvas');
annotations.forEach(a => {
  const rect = new fabric.Rect({
    left: a.x, top: a.y, width: a.w, height: a.h,
    fill: 'rgba(255, 215, 0, 0.3)', selectable: false
  });
  canvas.add(rect);
});
```

* Dynamically renders and removes highlights based on user searches.
* Maintains annotation state across zoom and pagination.
* Integrates seamlessly with AI metadata and PDF.js rendering.

This approach created **interactive, non-destructive overlays** — letting users click and explore AI-detected insights in real time.

---

### ⚙️ 2. Dynamic Data Visualization with D3.js

To complement the annotation layer, I implemented **D3.js charts** to visualize extracted data such as revenue trends, cost distributions, or ESG metrics.

* Used **reactive streams (RxJS)** to feed chart data live from Firestore.
* Built reusable **chart directives** for bar, line, and donut charts.
* Added **animated transitions** for clear user feedback when AI insights updated.

This transformed static AI outputs into **visual, interpretable intelligence**.

---

### ⚙️ 3. Realtime Sync & Firebase Integration

To handle collaborative workflows:

* Used **Firestore listeners** for live document updates and shared annotations.
* Implemented **offline persistence** and queued syncs for users working without connection.
* Integrated **Firebase Storage** for large PDF files with progress-bar uploads and resumable transfers.

This made the app **robust, collaborative, and reliable** — crucial for enterprise clients working with sensitive financial data.

---

### ⚙️ 4. Optimized Performance & Rendering

* Added **virtual scrolling** for multi-page PDFs to reduce memory footprint.
* Used **OnPush change detection** to prevent redundant re-renders.
* Batched annotation updates using `requestAnimationFrame()` for smoother drawing.
* Lazy-loaded analytics modules to keep the initial bundle lightweight.

---

## 🏁 Outcome

Ethos became a **smart AI companion for financial analysts and auditors**, turning dense PDF reports into **interactive, data-driven documents**.
The combination of **AI extraction**, **real-time annotations**, and **data visualization** helped companies **save hours per report** and **discover insights instantly**.

As the **sole front-end engineer**, I delivered a production-ready, scalable solution integrating **AI, visualization, and document intelligence** into a seamless user experience.

