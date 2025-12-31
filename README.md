# Crypto Golden Formula Trading System

多層次加密貨幣量化交易系統，基於機器學習的開單點位預測。

## 項目結構

```
crypto-golden-formula-trading/
├── data/
│   ├── raw/                 # 原始數據 (HF datasets)
│   ├── processed/           # 處理後的特徵數據
│   └── backtest_results/    # 回測結果
├── formulas/
│   ├── golden_formula_v1.py    # 第一套黃金公式
│   ├── golden_formula_v2.py    # 第二套黃金公式 (待開發)
│   └── formula_optimizer.py    # 公式優化器
├── indicators/
│   ├── custom_indicators.py    # 自訂指標
│   └── tv_integration.py       # TradingView 集成
├── ml_models/
│   ├── feature_engineering.py  # 特徵工程
│   ├── model_training.py       # 模型訓練
│   ├── ensemble_models.py      # 集成模型 (LSTM, XGBoost, RF)
│   └── saved_models/           # 模型權重存儲
├── backtest/
│   ├── backtester.py          # 回測引擎
│   ├── risk_management.py     # 風險管理 (1:1.5)
│   └── performance_metrics.py # 性能指標
├── config/
│   ├── settings.py            # 配置管理
│   └── constants.py           # 常數定義
└── notebooks/
    ├── data_exploration.ipynb
    ├── formula_research.ipynb
    └── model_development.ipynb
```

## 開發階段

### 階段 1：黃金公式設計（2-3週）
- [ ] 搜尋並分析最新加密貨幣量化公式論文
- [ ] 演算法反向生成第一套公式
- [ ] 演算法反向生成第二套公式
- [ ] 公式回測驗證

### 階段 2：TradingView 指標開發（3-4週）
- [ ] Pine Script 編寫
- [ ] 指標組合測試
- [ ] API 整合

### 階段 3：機器學習模型（4-6週）
- [ ] 特徵工程
- [ ] 模型訓練
- [ ] Ensemble 構建

### 階段 4：整合與優化（2-3週）
- [ ] 完整管道測試
- [ ] 紙交易驗證
- [ ] 性能優化

## 交易參數

- **交易標的**：Bitcoin (BTCUSDT)
- **時間框架**：15分鐘
- **風險管理**：1:1.5 (獲利目標:止損)
- **資料來源**：Hugging Face (zongowo111/v2-crypto-ohlcv-data)
- **數據量**：BTC 15m 歷史 OHLCV

## 依賴環境

```bash
pip install -r requirements.txt
```

## 核心論文與方法

本項目融合兩種方法論：
1. **學術論文導向**：搜尋並採用最新的量化交易研究成果
2. **演算法反向優化**：通過機器學習對歷史數據進行擬合，自動發現最優參數組合

## 使用指南

### 1. 數據準備
```python
from data_loader import load_btc_data
df = load_btc_data('BTC_15m')
```

### 2. 生成黃金公式
```python
from formulas.golden_formula_v1 import GoldenFormulaV1
formula = GoldenFormulaV1()
signals = formula.generate_signals(df)
```

### 3. 訓練 ML 模型
```python
from ml_models.model_training import ModelTrainer
trainer = ModelTrainer()
model = trainer.train(df, signals)
```

### 4. 回測
```python
from backtest.backtester import Backtester
backtester = Backtester()
results = backtester.run(df, signals, model)
```

## 許可證

MIT License

## 作者

軟體工程師 (Kaohsiung, Taiwan)