# Suggested run order

This package is primarily designed for auditability. A full rerun may require path editing in the copied YAML files.

1. Build or inspect UHSM products:
   `python scripts/build_uhsm.py`

2. Build or inspect generalized networks:
   `python scripts/build_generalized_sewer.py`

3. Run retained Xiaozhai model comparison:
   `python scripts/run_control_model_comparison.py`

4. Run retained capacity-control diagnostics:
   `python scripts/run_revision_m2_capacity_control.py`
   `python scripts/run_revision_capacity_sensitivity.py`

5. Run Zhengzhou event replay:
   `python scripts/run_zhengzhou720_event_replay.py`

6. Run DDSC assessment:
   `python scripts/build_ddsc_assessment_grid.py`
   `python scripts/aggregate_model_support_to_grid.py`
   `python scripts/run_ddsc_credibility_assessment.py`

7. Regenerate manuscript figures:
   `python scripts/plot_results_4_1_public_data_inputs.py`
   `python scripts/plot_results_4_2_1_uhsm_effect_2x2_zoom_cellwise.py`
   `python scripts/plot_results_4_2_2_drainage_representation.py`
   `python scripts/plot_results_4_3_public_evidence_credibility.py`
   `python scripts/plot_results_4_4_1_sensitivity_uncertainty.py`
   `python scripts/plot_results_4_4_2_cross_city_reproducibility.py`
