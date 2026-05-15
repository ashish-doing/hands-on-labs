Copy this resutls file and paste it into your own repo to showcase your results! Lab results do not count towards your score you'll receive for your submission, but we encourage you to show off what you learned in the lab!
# Add your experiment results and reflections here

# TORCS Lab Results — Ashish Kumar (@ashish-doing)

## Track: CG Speedway Number 1

| Metric | Value |
|--------|-------|
| Best Lap Time | 1:13:07 |
| Top Speed | 135 km/h |
| Laps Completed | 10 clean |
| Crashes | 0 |
| Total Race Time | 11:16:95 |

## Approach
Modular rule-based driver with:
- Proportional braking based on corner angle (not flat braking)
- Track sensor lookahead (`track[9]`) to detect walls ahead
- Traction control via wheel spin velocity differential
- Optimized gear shift points for this track

## Key Parameters
TARGET_SPEED = 135
STEER_GAIN = 25
CENTERING_GAIN = 0.50
BRAKE_THRESHOLD = 0.26
GEAR_SPEEDS = [0, 25, 45, 75, 110, 170]
ENABLE_TRACTION_CONTROL = True

## vs Baseline

| Driver | Best Lap | Crashes |
|--------|----------|---------|
| Default agent | DNF (cuts corners) | Many |
| MonDragons (prev best) | 1:47:84 | Multiple |
| This submission | 1:13:07 | 0 |

Improvement: -34 seconds vs previous best

## What I Learned
- Track sensors give valuable lookahead for preemptive braking
- Proportional braking outperforms threshold braking significantly
- Small parameter changes (TARGET_SPEED 120→135) compound over 10 laps
- Traction control prevents wheelspin on acceleration out of corners
