# Predicting Roadside Emissions Using Spatiotemporal Neural Networks: A Case Study in London

**Master's Thesis**  
**Supervisor:** Prof. Ana Varela Varela, Department of Geography and Environment, LSE  
**Keywords:** air quality forecasting, spatiotemporal data modeling, Graph Attention Network (GAT), LSTM  

---

## Project Overview
This study explores the prediction of NO<sub>2</sub> concentrations at roadside monitoring stations in London. Utilizing spatiotemporal neural networks and trained using a spatiotemporal dataset of hourly air pollutant concentrations collected from the [London Air Quality Network (LAQN)](https://www.londonair.org.uk/london/asp/publicdetails.asp), this study aims to improve air quality predictions by modeling both spatial and temporal dependencies in air pollutant dispersion. The study offers a data-driven approach for enhancing transportation policy and urban planning efforts by better understanding emission patterns.


### Key Contributions
- **Compiled** a comprehensive feature set, categorizing data into spatial static features (e.g., road conditions, traffic characteristics) and temporal features (e.g., historical emissions, weather conditions).
- **Developed** a spatiotemporal dynamic graph, accounting for geographical proximity and wind-driven dispersion.
- **Designed** a hybrid model combining Long Short-Term Memory (LSTM) networks and Graph Attention Networks (GAT), which outperformed traditional baselines.

### Results   
The proposed model (REGAL) outperforms existing baselines in prediction accuracy. Specifically, the graph attention mechanism improves accuracy by 12.5% and the encoder-decoder architecture in LSTM extends the forecast horizon to 12 hours, with superior performance in long-term (9-12h) predictions over short-term (1-4h).  
<table>
  <tr>
    <th>Model</th>
    <th>Time Granularity</th>
    <th>RMSE</th>
    <th>MAE</th>
    <th>PCC</th>
  </tr>
  <tr>
    <td rowspan="3">VAR</td>
    <td>1-4h</td>
    <td>14.31±0.00</td>
    <td>12.56±0.00</td>
    <td>0.70±0.00</td>
  </tr>
  <tr>
    <td>5-8h</td>
    <td>15.46±0.00</td>
    <td>13.89±0.00</td>
    <td>0.54±0.00</td>
  </tr>
  <tr>
    <td>9-12h</td>
    <td>24.61±0.00</td>
    <td>23.58±0.00</td>
    <td>0.46±0.00</td>
  </tr>
  <tr>
    <td rowspan="3">MLP</td>
    <td>1-4h</td>
    <td>12.46±0.12</td>
    <td>9.42±0.12</td>
    <td>0.71±0.01</td>
  </tr>
  <tr>
    <td>5-8h</td>
    <td>14.51±0.2</td>
    <td>11.06±0.16</td>
    <td>0.58±0.01</td>
  </tr>
  <tr>
    <td>9-12h</td>
    <td>15.64±0.2</td>
    <td>12.04±0.13</td>
    <td>0.49±0.01</td>
  </tr>
  <tr>
    <td rowspan="3">GCN</td>
    <td>1-4h</td>
    <td>10.16±0.05</td>
    <td>7.44±0.04</td>
    <td>0.82±0.0</td>
  </tr>
  <tr>
    <td>5-8h</td>
    <td>13.03±0.25</td>
    <td>9.7±0.2</td>
    <td>0.68±0.01</td>
  </tr>
  <tr>
    <td>9-12h</td>
    <td>14.35±0.53</td>
    <td>10.78±0.42</td>
    <td>0.59±0.03</td>
  </tr>
  <tr>
    <td rowspan="3">GRU</td>
    <td>1-4h</td>
    <td>9.87±0.18</td>
    <td>7.05±0.19</td>
    <td>0.83±0.01</td>
  </tr>
  <tr>
    <td>5-8h</td>
    <td>12.85±0.18</td>
    <td>9.46±0.19</td>
    <td>0.7±0.01</td>
  </tr>
  <tr>
    <td>9-12h</td>
    <td>13.43±0.18</td>
    <td>10.02±0.19</td>
    <td>0.67±0.01</td>
  </tr>
  <tr>
    <td rowspan="3">HighAir</td>
    <td>1-4h</td>
    <td>9.8±0.12</td>
    <td>7.1±0.06</td>
    <td>0.83±0.01</td>
  </tr>
  <tr>
    <td>5-8h</td>
    <td>12.74±0.06</td>
    <td>9.45±0.03</td>
    <td>0.71±0.0</td>
  </tr>
  <tr>
    <td>9-12h</td>
    <td>13.59±0.39</td>
    <td>10.08±0.22</td>
    <td>0.67±0.01</td>
  </tr>
  <tr>
    <td rowspan="3">REGAL</td>
    <td>1-4h</td>
    <td><b>9.46±0.01</b></td>
    <td><b>6.75±0.05</b></td>
    <td><b>0.84±0.0</b></td>
  </tr>
  <tr>
    <td>5-8h</td>
    <td><b>12.01±0.19</b></td>
    <td><b>8.92±0.22</b></td>
    <td><b>0.74±0.01</b></td>
  </tr>
  <tr>
    <td>9-12h</td>
    <td><b>12.63±0.2</b></td>
    <td><b>9.44±0.21</b></td>
    <td><b>0.71±0.01</b></td>
  </tr>
</table>

