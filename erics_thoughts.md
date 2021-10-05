# High Level Idea

I think the first thing we should do is build a functional api for machine learning models.  Then we go through and create some reference architectures for specific problems.  Creating examples will help guide folks to approximately correct architectures.  From here we can use transfer learning, as suggested to create a hub of architectures for different models.  I think including metrics on the relevant dataset will let folks know how the model performs.  And then some associated analysis explaining *why* the model works.

I think we could leverage functional programming notions to build the models.  This will allow us to provide type information to the models themselves, which may aid in problem solving.  

## Details For ML models

It will probably be easist to go in this order:

* least squares regression
	* linear regression
	* polynomial regression

* trees
	* decision trees
	* random forests
	* gradient boosting trees

* neural nets
	* vanilla
	* RNN
	* CNN
	* LSTM
	* Attention
	* Auto Encoders
	* Transformer
	* Variational Auto Encoders
	* Capsule Networks
	* Graph Neural Networks
	* Equivariant Graph Neural Networks

* Symbolic Regression
* Evolutionary Algorithms

## Type Theory and API Design

Things like:
* [penrose notation](https://www.math3ma.com/blog/matrices-as-tensor-network-diagrams) provide rich ground from which to build compositional neural networks.
* [optics](https://hackage.haskell.org/package/optics-0.4/docs/Optics.html) I believe will be directly useful, specifically the subtype hierarchy diagram in the above reference.  If we implement this set of primitives, we can think about our mathematical operations compositionally.  Where I think i'd like to differ from traditional functional programming - instead of relying on minimal syntax, which can often make it hard to get started, I believe using explicit names for these functions is an imperative.
* [optics and lenses](https://golem.ph.utexas.edu/category/2020/01/profunctor_optics_the_categori.html) provides a great example of using category theory for string processing.  Again, I don't like the syntax, but I think the notions here are immediately useful.  

Overall, I think this syntax will give us something like a superset of einstein notation which we can use to express many vector transforms, and _even_ non-linear transforms.

Einstein notation references:
* http://www.ees.nmt.edu/outside/courses/GEOP523/Docs/index-notation.pdf
* https://en.wikipedia.org/wiki/Einstein_notation
* https://numpy.org/doc/stable/reference/generated/numpy.einsum.html

## Reference Architectures

For this I think the reference architectures should serve as examples, showing how 