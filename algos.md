
| Alg | P/NP | D/G | Sup | Task | Dom | Lin | Prob | Lazy | Cvx | Kern | Scale | Interp | Robust | Online | MC | Miss | Cal | FI | Reg | Assump | Comp (fit/pred) | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| OLS (LinReg) | P | D | S | Reg | Tab | Y | Y | N | Y | N | ~ | H | L | ~ | – | N | – | Coef | – | Lin, Gauss, Hm | O(nd) / O(d) | baseline |
| Ridge | P | D | S | Reg | Tab | Y | Y | N | Y | N | ~ | H | M | ~ | – | N | – | Coef | L2 | Lin, Gauss | O(nd) / O(d) | shrinks coef |
| Lasso | P | D | S | Reg | Tab | Y | Y | N | Y | N | ~ | H | M | ~ | – | N | – | Coef | L1 | Lin, Gauss | O(nd) / O(d) | sparse |
| Logistic Reg | P | D | S | Clf | Tab/Txt | Y | Y | N | Y | ~ | Y | H | M | ~ | Native | N | Y | Coef | L2/L1 | Lin, Margin | O(nd)/O(d) | calibrated baseline |
| LDA | P | G | S | Clf | Tab | Y | Y | N | Y | N | Y | M | L | N | Native | N | Y | Coef | – | Gauss, EqualCov | O(nd)/O(d) | closed-form |
| QDA | P | G | S | Clf | Tab | N | Y | N | Y | N | Y | M | L | N | Native | N | Y | Coef | – | Gauss | O(nd²)/O(d²) | quad boundary |
| NB (Gaussian) | P | G | S | Clf | Tab | ~ | Y | N | – | N | ~ | M | L | Y | Native | N | N | – | Prior | Indep, Gauss | O(nd)/O(d) | very fast |
| NB (Multi/Bern) | P | G | S | Clf | Txt | ~ | Y | N | – | N | N | M | L | Y | Native | N | N | – | Prior | Indep | O(nd)/O(d) | BoW text |
| k-NN | NP | D | S | Both | Tab/Img/Txt | N | N | Y | – | N | Y | L | L | N | Native | N | – | No | – | Local | fit O(1)/pred O(nd) | memory-based |
| Perceptron | P | D | S | Clf | Tab/Txt | Y | N | N | ? | N | Y | M | L | Y | OvR | N | N | Coef | L2 | Sep, Margin | O(nd)/O(d) | linear, online |
| SVM (linear) | P | D | S | Both | Tab/Txt | Y | N | N | Y | N | Y | M | M | ~ | OvR/OvO | N | Needs | Coef | L2 | Margin | ~O(n²d)/O(d) | margin-based |
| SVM (RBF) | NP | D | S | Both | Tab | N | N | N | Y | Y | Y | L | M | N | OvO | N | Needs | No | C | Margin, Smooth | O(n²–n³)/O(s) | uses SVs |
| Decision Tree | NP | D | S | Both | Tab | Loc | ~ | N | N | N | N | H | M | N | Native | ~ | N | Y | Depth/Prune | Axis | O(nd log n)/O(D) | rules |
| Random Forest | NP | D | S | Both | Tab | N | ~ | N | N | N | N | M | H | ~ | Native | ~ | ~ | Y/Perm | Depth | Axis, Bagging | O(T n log n)/O(TD) | OOB, robust |
| GBDT (XGB/LGBM) | NP | D | S | Both | Tab | N | ~ | N | N | N | N | M | M | ~ | Native | Y | ~ | Y/SHAP | Shrink/Depth | Add | O(T n log n)/O(TD) | SOTA tabular |
| GP (GPR/GPC) | NP | G | S | Both | Tab/Time | N | Y | N | Y | Y | Y | M | M | N | Native | N | Y | No | Priors | Smooth | O(n³)/O(n) | uncertainty |
| k-means | P | – | U | Clus | Tab/Img | N | N | N | N | N | Y | M | L | Y | – | N | – | No | – | Sph, LinSep | O(nkdi)/O(kd) | centroid, fast |
| GMM | P | G | U | Clus/Dens | Tab | N | Y | N | N | N | Y | M | L | ~ | – | N | – | No | Priors | Gauss mix | O(nkdi)/O(kd) | soft clusters |
| DBSCAN | NP | – | U | Clus/Anom | Tab | N | N | N | N | N | Y | L | M | N | – | N | – | No | – | Density | O(n log n)/O(log n) | noise aware |
| PCA | P | – | U | DR | Tab/Img | Y | N | N | Y | N | Y | M | L | ~ | – | N | – | Load | – | VarMax | O(nd²+d³)/O(md) | linear DR |
| t-SNE | NP | – | U | DR/Vis | Tab/Img/Txt | N | ~ | N | N | N | Y | L | M | N | – | N | – | No | – | Manifold | O(n²)/– | visualization |
| UMAP | NP | – | U | DR/Vis | Tab/Img/Txt | N | ~ | N | N | N | Y | L | M | N | – | N | – | No | – | Manifold | ~O(n log n)/– | faster than t-SNE |
| HMM | P | G | S/U | Seq/Clf | Time/Txt | N | Y | N | N | N | Y | M | L | ~ | Native | N | – | No | Priors | Markov, Station | O(L S²)/O(L S²) | temporal gen |
| CRF (lin-chain) | P | D | S | Seq | Txt/Time | Y | Y | N | Y | N | Y | M | M | ~ | Native | N | Y | Weights | L2/L1 | Markov | O(it·L S²)/O(L S²) | structured pred |
| MLP (feed-fwd NN) | P | D | S | Both | Tab/Txt/Img | N | ~ | N | N | N | Y | L | L | Y | Native | N | N | SHAP/No | Drop/L2/EStop | – | O(E·P)/O(P) | flexible |
| CNN | P | D | S | Both | Img/Time | N | ~ | N | N | N | ~ | L | L | Y | Native | N | N | Saliency | Drop/Aug | Locality | heavy/– | conv features |
| RNN/LSTM/GRU | P | D | S | Both/Seq | Time/Txt | N | ~ | N | N | N | Y | L | L | Y | Native | N | N | No | Drop | Markovish | O(E·P)/O(P) | sequences |
| Transformer | P | D | S/SL | Both/Seq | Txt/Img/Time | N | ~ | N | N | N | Y | L | L | Y | Native | N | N | No | Drop | – | O(E·n²·d)/O(n²·d) | attn-based |
| GNN (GCN/GAT) | P | D | S | Both | Graph | N | ~ | N | N | N | Y | L | M | ~ | Native | N | N | No | Drop | Smooth | O(E·P)/O(P) | graph reps |
| Autoencoder (AE) | P | – | U/SL | DR/Anom | Txt/Img/Tab | N | N | N | N | N | Y | L | M | Y | – | N | – | No | Drop | Manifold | O(E·P)/O(P) | reps |
| Isolation Forest | NP | – | U | Anom | Tab | N | N | N | N | N | N | M | H | ~ | – | ~ | – | Y/Perm | Depth | Axis, Random | O(T n log n)/O(TD) | isolates outliers |
| One-Class SVM | NP | D | U | Anom | Tab | N | N | N | Y | Y | Y | L | M | N | – | N | – | No | ν | Margin, Smooth | O(n²–n³)/O(s) | boundary on normal |
| ARIMA | P | G | S | Reg/Fore | Time | Y | Y | N | Y | N | Y | M | L | ~ | – | N | – | – | – | Station | O(n)/O(1) | classical TS |
| Kalman Filter | P | G | S/U | Seq/Fore | Time | Y | Y | N | Y | N | Y | M | M | Y | – | N | – | – | Priors | Gauss, Lin | O(n d³)/O(d²) | state-space |
