# Assignment 1

## Task 1 -- Acquisition

**Process the IF data using a GNSS SDR and generate initial acquisition outputs.**

1. **Open air results:**

   ![Open Air Results](media/image1.png)

2. **Urban results:**

   ![Urban Results](media/image2.png)

## Task 2 -- Tracking

**Adapt the tracking loop (DLL) to produce correlation plots and analyze the tracking performance. Discuss the impact of urban interference on the correlation peaks. (Multiple correlators must be implemented for plotting the correlation function)**

1. **Open air results:**

   ![Open Air Tracking Results](media/image3.png)

2. **Urban results:**

   ![Urban Tracking Results](media/image4.png)

3. **The impact of urban interference on the correlation peaks:**

   a. Firstly, the values of Auto-correlation functions (ACF) in urban areas are much smaller than most of the ACF values in open sky areas, which is because the propagation of signals in open sky areas suffered less interference.

   b. Secondly, the variation of ACF values in urban areas are less than that in open sky areas. This is probably due to that the signals that encounter interference in urban environments are not tracked, only the reliable satellites are received, causing a survivorship bias.

## Task 3 -- Navigation data decoding

- **Table showing the decoded ephemeris parameters for urban experiment:**

  (Table content not provided in the original document)

## Task 4 -- Position and velocity estimation

1. **Open air results:**

   a. **Position**

   ![Open Air Position](media/image5.png)

   ![Open Air Position Graph](media/image6.png)

   b. **Velocity**

   ![Open Air Velocity](media/image7.png)

2. **Urban results:**

   a. **Position**

   ![Urban Position](media/image8.png)

   ![Urban Position Graph](media/image9.png)

   b. **Velocity**

   ![Urban Velocity](media/image10.png)

3. **The impact of multipath effect on the WLS solution:**

   The positioning errors in open sky areas are mostly less than 30 meters, while in urban areas are large to 100 meters. In urban areas, the error in East direction is extremely large, which is due to the blockage of satellites in the west by buildings, which makes the PDOP very large in urban areas.

## Task 5 -- Kalman filter-based positioning

1. **Open air results:**

   a. **Position**

   ![Open Air Kalman Position](media/image11.png)

   b. **Velocity**

   ![Open Air Kalman Velocity](media/image12.png)

2. **Urban results:**

   a. **Position**

   ![Urban Kalman Position](media/image13.png)

   b. **Velocity**

   ![Urban Kalman Velocity](media/image14.png)

3. **EKF using pseudorange and Doppler**

   a. The doppler shift measurements can be calculated as the difference between the carrier frequency tracked by SDR and the designed transmitted carrier frequency.

   b. The velocity estimation method is based on a reference (Ji, L., Sun, R., Cheng, Q., & Wang, J. (2022). Evaluation of the performance of GNSS-based velocity estimation algorithms. Satellite Navigation, 3(1), 18. [https://doi.org/10.1186/s43020-022-00080-4](https://doi.org/10.1186/s43020-022-00080-4)).

   c. Velocity estimation method is realized in `rec_vel.m` file. EKF method is realized in `ekf_gnss.m` file. Baoshan Song contributed to part of the modification in `postNavigation.m` and `plotNavigation.m` files.

---

**Note:** The images referenced in this document are placeholders and should be replaced with the actual graphs and screenshots from the original document.
