# Elaborazione_dei_Segnali_Multimediali
SEN2-PFT-SR: modello di super-risoluzione per migliorare immagini satellitari con upscaling 4x

---

## Descrizione

SEN2-PFT-SR è un progetto realizzato per aumentare la qualità delle immagini satellitari a bassa risoluzione (LR) utilizzando un’architettura di **super-risoluzione (SR)**.  
Il modello produce immagini ad alta risoluzione (HR) mantenendo integrità strutturale e accuratezza spettrale, utili per analisi territoriali e identificazione di pannelli fotovoltaici.

---

## Obiettivo

- Migliorare la precisione delle analisi territoriali tramite upscaling 4x.  
- Identificare impianti fotovoltaici ≥500 m² nel territorio di Bologna. 

---

## Architettura

Il modello si basa sulla rete **Progressive Focused Attention (PFA)**:

- **Conv:** Estrae caratteristiche iniziali dall’immagine LR.  
- **PFAB (PFA Block):** Elabora le caratteristiche con attenzione focalizzata.  
- **PFAL × M:** Sequenza di M livelli di Progressive Focused Attention Layers.  
- **Upsample:** Ingrandisce l’immagine fino a 4x (utilizzando PixelShuffle).  
- **LayerNorm & MLP:** Normalizzano le caratteristiche e le processano localmente dopo l’attenzione.

**Meccanismo PFA:** calcola mappe di attenzione solo nelle aree importanti usando **Sparse Matrix Multiplication (SMM)** e **Hadamard product**.

---
 
**Metriche di valutazione:**  
- **Loss:** misura l’errore del modello durante l’apprendimento. La Loss utilizzata è la MAE.  
- **IoU Score (Intersection over Union):** verifica la capacità di rilevare correttamente gli oggetti.

---

## Sviluppi Futuri

- Migliorare la risoluzione fino a 6x/8x.  
- Ottimizzare la classificazione per pannelli più piccoli (ad es. tetti residenziali).  
- Estendere il modello a nuovi tipi di superfici e applicazioni.

---

## Tecnologie e Librerie

- Architettura Deep Learning con **PFA Blocks**   
- Framework: (PyTorch/TensorFlow da specificare)  
- Analisi delle performance tramite **Loss** e **IoU Score**

---

Professoressa: Luisa Verdoliva<br>
Università Federico II – A.A. 2024-2025

