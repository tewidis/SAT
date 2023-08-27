# Soundness and Completeness

## Soundness

1. Soundness: A sound analysis means we can trust the correctness of its output.
If it says a program is correct, the program is definitely correct. However, the
analysis may improperly say some programs are not correct.

## Trivially Sound Quiz

1. Trivially sound analysis rejects all inputs

``` C
bool trivialSoundAnalysis() {
    return false;
}
```

## Soundness Continued

1. Trivially sound analysis
    * Returns false for all inputs
2. Example: Verifying a car drive by wire/brake by wire system
    * Electrical connections instead of mechanical connections
        - Software controls the electrical connections
    * Need absolute confidence that the software controlling the acceleration
    and braking of your car is correct

## Completeness

1. Completeness: A complete analysis means we can trust that what it excludes
from its analysis is incorrect. If it says that a program is not correct, then
the program is definitely not correct. However, the analysis may improperly
say some incorrect programs are correct.

## Trivially Complete Quiz

1. Trivially complete analysis accepts all inputs

``` C
bool trivialCompleteAnalysis() {
    return true;
}
```

## Completeness and Perspective

1. Trivially complete analysis
    * Returns true for all inputs
2. Example: Analyzing if a fire alarm should trigger
3. Sound < Correct < Complete
    * All sound programs are correct
    * All correct programs are complete
4. False positive: We say a condition is true when it's actually false
5. False negative: We say a condition is false when it's actually true

| ![soundness](images/lesson1_soundness_completeness.png) |
|:--:|
| Soundness, Completeness, Correctness |

6. Error-containing vs Correct Programs
    * False positive/negative depends on the frame of reference

## Perspective Quiz

1. Order the items in the circle for an error-containing program instead of a
correct program
    * Sound
    * Error-containing
    * Complete

## Example Problems

1. Vibhuti is participating in a bug bounty program at her employer. For every
bug she finds using software analysis in production code, she gets $500. However,
she is banned from getting any rewards if she submits a bug and it is found to
be invalid. What kind of analysis should she use?
    * Desire: Certainty
    * Frame of reference: Correct software
    * Result: Sound analysis
2. Julio works for a paper manufacturer. The manufacturer has been having an
issue with the safety control programs causing the plant to shut down in error
at least every dat. Since each time the plant stops the company loses thousands
of dollars, Julio has been asked to use an analysis to prevent the plant from
stopping when there is no problem.
    * Desire: Certainty
    * Frame of reference: Error-containing software
    * Complete analysis

## Where Do We Go From Here?

1. Soundness and completeness will come up again
2. Be sure to consider the perspective of the analysis, what is being checked,
when using false positive or false negative!
