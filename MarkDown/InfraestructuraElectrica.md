# 🔢 Càlcul de consum elèctric i dimensionament del sistema SAI

## 1. ⚙️ Consum estimat del sistema

Comencem calculant el **consum estimat dels servidors** en funcionament habitual i en condicions de màxima càrrega:

- 🖥️ **Nombre de servidors actius**: 10
- ⚡ **Consum mitjà per servidor**: 700 W
- 🚀 **Consum màxim amb càrrega alta**: fins a 1.000 W
- 🛡️ **Margen de seguretat aplicat**: 20% per absorbir pics i garantir estabilitat

### 📐 Càlcul total de potència:

- `10 × 700 W = 7.000 W = 7 kW`

### ➕ Amb marge de seguretat del 20%:

- `7 kW × 1,2 = 8,4 kW`

### 🔋 Energia necessària per 3 hores d’autonomia:

- `8,4 kW × 3 h = 25,2 kWh`

👉 Per tant, necessitem un sistema SAI capaç de subministrar **25,2 kWh** per mantenir els servidors encesos durant **3 hores**, fins i tot si funcionen a plena capacitat.

---

## 2. 🔍 Selecció del sistema SAI

Per cobrir aquesta demanda energètica, busquem un sistema amb les característiques següents:

- ⚡ **Potència nominal**: 6 kVA
- ✅ **Factor de potència real**: 0,9 (90%)
- 🔌 **Potència efectiva**: 5,4 kW per unitat

### 🏷️ Model escollit:

- **SAI Lapara 6000VA / 6000W**
  - Proporciona **1 kW addicional** respecte al necessari
  - Ideal per situacions amb càrrega elevada de tots els servidors

---

## 3. 💰 Cost del sistema

- 💵 **Preu per unitat**: 1.647,09 €
- 🔢 **Nombre d’unitats necessàries**: 5
- 💸 **Cost total estimat**:  
  `1.647,09 € × 5 = 8.235,45 €`

---

<p align="center" style="margin-top: 40px;">
  <a href="./calculoAnterior.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      ⬅️ Càlcul anterior
    </button>
  </a>
  
  <a href="../README.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      | 🏠 Inici |
    </button>
  </a>
  
  <a href="./instalacionSAI.md" style="text-decoration: none; margin-left: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #4CAF50; color: white; border: none;">
      Següent càlcul ➡️
    </button>
  </a>
</p>
