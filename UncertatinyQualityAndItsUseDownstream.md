# Question
how much does calibration quality, and single-pass method in particular, matter downstream, and what happens when it fails?

# Novelty 

* Whether measurement-level ranking predicts graph-level ranking.
  * If the method with the best NLL or ECE is not the one with the best NEES or dock success, that is a real finding. It also argues against evaluating UQ on calibration alone.
* Sensitivity of the graph to miscalibration.
  * Scale σ by 0.25× to 4× and plot error, NEES and dock success. This shows how much calibration you need.
* Overconfident-but-wrong behavior.
  * Under OOD and fault injection, quantify how often σ is small and the error is large, and what that does to the graph. This fits our PhD theme.
* Single-pass versus ensembles or MC dropout.
  * Report estimation quality per millisecond and per watt on the embedded target. This is  strongest angle but its obvious.
* Soft versus hard use of uncertainty.
  * Compare σ-weighting only, gating, and monitor-triggered fallback (stop or back off). Link this t our monitor paper.
 
# EU AI act 
No Conformanace !
claim is that the results provide evidence toward specific obligations or processes:

* SOTIF (ISO 21448): the uncertainty monitor acts as a mitigation for performance insufficiencies. Your fault and OOD set stands in for triggering conditions. You would need to argue coverage of a triggering-condition taxonomy and show residual risk, for example false-accept rate at hazardous states.
* AI Act: the monitor and its metrics could support Art. 15 (accuracy and robustness), Art. 9 (risk management) and Art. 14 (oversight). Whether  system is high-risk depends on the application, and the harmonised standards are still pending, so hedge this.
* Scope: SOTIF is for road vehicles. For a docking robot, also cite ISO 3691-4 or ISO 13482, and optionally UL 4600 or ISO/PAS 8800 for the AI-specific parts. Check the current status of all of these before submitting.
