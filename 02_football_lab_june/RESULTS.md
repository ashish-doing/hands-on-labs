# June Football Lab — Results

## Tasks completed
1. Installed pandas, scikit-learn, streamlit, joblib, requests
2. Downloaded international football results dataset (1872–2026, ~49k matches)
3. Explored tournament types, top teams by matches played, matches per decade
4. Engineered time-safe features: team win rate, goal average, recent form
   (last 10 matches), neutral venue flag, major-tournament flag — all computed
   using only data strictly before each match (no lookahead leakage)
5. Time-based train/test split: train on pre-2018 matches, test on 2018+
6. Trained a RandomForestClassifier (200 trees, max depth 12) on 3-class
   outcome (home win / draw / away win), benchmarked against majority-class
   baseline, inspected feature importances
7. Saved trained model + per-team stats (filtered to World Cup–eligible teams)
8. Tested predict_match() on sample fixtures (Brazil vs Argentina, Germany vs Brazil)
9. Built a Streamlit UI for interactive match prediction with live probability
   bars and team stats table
10. Launched the UI locally and verified end-to-end

## Key takeaway
Historical win rate and recent form were the strongest predictors —
stronger than raw goal average. Reinforced the importance of strict
temporal validation (no random shuffling across years) and reporting an
honest baseline comparison, both of which carried directly into my June
challenge submission (FineMargins), which goes further by explicitly
reporting where pressure-context prediction breaks down (AUC 0.518 on
individual penalty outcomes) rather than hiding that limitation.