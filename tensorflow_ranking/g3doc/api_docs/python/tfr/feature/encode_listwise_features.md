<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfr.feature.encode_listwise_features" />
<meta itemprop="path" content="Stable" />
</div>

# tfr.feature.encode_listwise_features

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/ranking/tree/master/tensorflow_ranking/python/feature.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>

Returns dense tensors from features using feature columns.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tfr.feature.encode_listwise_features(
    features, context_feature_columns, example_feature_columns, input_size=None,
    mode=tf.estimator.ModeKeys.TRAIN, scope=None
)
</code></pre>

<!-- Placeholder for "Used in" -->

<!-- Tabular view -->

 <table class="properties responsive orange">
<tr><th colspan="2"><h2 class="add-link">Args</h2></th></tr>

<tr>
<td>
`features`
</td>
<td>
(dict) mapping feature names (str) to feature values (`tf.Tensor`
or `tf.SparseTensor`), possibly obtained from input_fn. For context
features, the tensors are 2-D, while for example features the tensors are
3-D.
</td>
</tr><tr>
<td>
`context_feature_columns`
</td>
<td>
(dict) context feature names to columns.
</td>
</tr><tr>
<td>
`example_feature_columns`
</td>
<td>
(dict) example feature names to columns.
</td>
</tr><tr>
<td>
`input_size`
</td>
<td>
(int) [DEPRECATED: Use without this argument.] number of
examples per query. If this is None, input_size is inferred as the size
of second dimension of the Tensor corresponding to one of the example
feature columns.
</td>
</tr><tr>
<td>
`mode`
</td>
<td>
(`estimator.ModeKeys`) Specifies if this is training, evaluation or
inference. See `ModeKeys`.
</td>
</tr><tr>
<td>
`scope`
</td>
<td>
(str) variable scope for the per column input layers.
</td>
</tr>
</table>

<!-- Tabular view -->

 <table class="properties responsive orange">
<tr><th colspan="2"><h2 class="add-link">Returns</h2></th></tr>

<tr>
<td>
`context_features`
</td>
<td>
(dict) A mapping from context feature names to dense
2-D tensors of shape [batch_size, ...].
</td>
</tr><tr>
<td>
`example_features`
</td>
<td>
(dict) A mapping from example feature names to dense
3-D tensors of shape [batch_size, input_size, ...].
</td>
</tr>
</table>

<!-- Tabular view -->

 <table class="properties responsive orange">
<tr><th colspan="2"><h2 class="add-link">Raises</h2></th></tr>

<tr>
<td>
`ValueError`
</td>
<td>
If `input size` is not equal to 2nd dimension of example
tensors.
</td>
</tr>
</table>
