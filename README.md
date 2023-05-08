# TFP CausalImpact

This Python package implements an approach to estimating the causal effect of a
designed intervention on a time series.  For example, how many additional daily
clicks were generated by an advertising campaign? Answering a question like this
can be difficult when a randomized experiment is not available. The package aims
to address this difficulty using a structural Bayesian time-series model to
estimate how the response metric might have evolved after the intervention if
the intervention had not occurred [1].

As with all approaches to causal inference on non-experimental data, valid
conclusions require strong assumptions. The CausalImpact package, in particular,
assumes that the outcome time series can be explained in terms of a set of
control time series that were themselves not affected by the intervention.
Furthermore, the relation between treated series and control series is assumed
to be stable during the post-intervention period. Understanding and checking
these assumptions for any given application is critical for obtaining valid
conclusions.

TFP CausalImpact is a Python +
[TensorFlow Probability](https://github.com/tensorflow/probability)
implementation of the
[CausalImpact](https://google.github.io/CausalImpact/) R package developed at
Google by Kay Brodersen and Alain Hauser.  TFP CausalImpact is based on both
the original R package and on a Python version
https://github.com/dafiti/causalimpact developed at Dafiti by Willian Fuks.
TFP CausalImpact was developed at Google by Colin Carroll, David Moore,
Jacob Burnim, Kyle Loveless, and Susanna Makela.

*This is not an officially supported Google product.*

[1] _Inferring causal impact using Bayesian structural time-series models._
    Kay H. Brodersen, Fabian Gallusser, Jim Koehler, Nicolas Remy,
    Steven L. Scott.  Annals of Applied Statistics, vol. 9 (2015), pp. 247-274.
    https://research.google/pubs/pub41854/


## Getting Started

TFP CausalImpact can be installed via `pip`:

```
pip install tfp-causalimpact
```

And imported as:

```
import causalimpact
```

See also the [Quick-Start Guide](https://github.com/google/tfp-causalimpact/blob/main/docs/quickstart.ipynb).


## Development

Clone TFP CausalImpact, install the development dependencies, and run the unit
tests with:

```
git clone https://github.com/google/tfp-causalimpact.git tfp_causalimpact
cd tfp_causalimpact

pip install flit
flit install --only-deps

pytest -vv -n auto
```
