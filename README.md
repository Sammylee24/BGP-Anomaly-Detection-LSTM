# The Blind Spot of BGP Anomaly Detection: Why LSTM Autoencoders Fail on Real-World Outages

This repository contains the code and resources for the research paper exploring the effectiveness and limitations of LSTM autoencoders for detecting real-world BGP anomalies.

**Author:** Samuel Oluwafemi Adebayo
**Contact:** adebayosamueloluwafemi1@gmail.com
**LinkedIn:** https://www.linkedin.com/in/samuel-adebayo1/

**Paper:** https://github.com/Sammylee24/BGP-Anomaly-Detection-LSTM/blob/main/Adebayo_BGP_Anomaly_Detection_Paper.pdf

---

## Abstract

Deep learning has significant potential to make the Internet's Border Gateway Protocol (BGP) secure by detecting anomalous routing activity. However, all but a few of these approaches rely on the implicit assumption that anomalies manifest as noisy, high-complexity outliers from some normal baseline. This work challenges this assumption by investigating if a best-in-class detection model built on this assumption can effectively deal with real-world security events' diverse signatures. We employ an LSTM-based autoencoder, a classical example of a reconstruction-based anomaly detector, as our test vehicle. We then contrast this model with a representative sampling of historical BGP anomalies, including the Slammer worm and the Moscow blackout, and with a simulated 'BGP storm' designed as a positive control. Our experience unveils a blind spot of our model: the model easily identifies the synthetic anomaly of high complexity but invariably fails to identify real-world events that manifest in the form of a "signal loss" (e.g., Slammer, Moscow Blackout) or "low-deviation" (e.g., WannaCry) signature. We demonstrate that the model mistakenly recognizes the abrupt cut-off of BGP updates during catastrophic failures as a signal of extreme stability, leading to reconstruction errors of virtually zero and total failure to detect. We conclude that the characterization of BGP anomalies as high-reconstruction-error events alone is a weak and dangerous oversimplification. Our research provides the data-driven case for why hybrid, multi-modal detection systems capable of identifying both high-complexity and signal-loss signatures are required to enable end-to-end BGP security.


---

## Repository Contents

*   `Adebayo_BGP_Anomaly_Detection_Paper.pdf`: The full research paper.
*   `BGP_Anomaly_Detection_Analysis.ipynb`: The Python Jupyter Notebook containing all code for data processing, model training, and evaluation.
*   `BGP_Storm_Anomaly.csv`: The synthetic anomaly dataset generated to serve as a positive control.
*   `requirements.txt`: A list of the Python libraries required to run the code.

---

## How to Reproduce the Results

1.  **Download the Original Dataset:** The real-world anomaly data (WannaCry, Slammer, etc.) is from the public "BGP RIPE Datasets for Anomaly Detection" by Li, Gonzalez Rios, and Trajkovic. It can be downloaded from: http://www.sfu.ca/~ljilja/cnl/projects/BGP_datasets/index.html
2.  Download the zip file and extract it into a folder named `BGP_RIPE_datasets_for_anomaly_detection_csv_revised_19022021/` in the same directory as the notebook.

3.  **Install Dependencies:** The required Python libraries are listed in `requirements.txt`. Install them using pip:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Notebook:** Open `BGP_Anomaly_Detection_Analysis.ipynb` in a Jupyter or Google Colab environment and execute the cells in order. The notebook will generate the synthetic data and all the figures presented in the paper.

---

## Citation

If you use this work, please cite the paper:

Adebayo, S. O. (2025). The Blind Spot of BGP Anomaly Detection: Why LSTM Autoencoders Fail on Real-World Outages.
