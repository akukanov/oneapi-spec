.. _math_notations:

======================
Mathematical Notations
======================

.. list-table::
   :widths: 15 85
   :header-rows: 1

   * - Notation
     - Definition

   * - :math:`n` or :math:`m`
     - The number of :term:`observations <Observation>` in a
       :term:`dataset <Dataset>`. Typically :math:`n` is used, but sometimes
       :math:`m` is required to distinguish two datasets, e.g., the
       :term:`training set <Training set>` and the :term:`inference set
       <Inference set>`.

   * - :math:`p` or :math:`r`
     - The number of features in a dataset. Typically :math:`p` is used, but
       sometimes :math:`r` is required to distinguish two datasets.

   * - :math:`a \times b`
     - The dimensionality of a matrix (dataset) has :math:`a` rows
       (observations) and :math:`b` columns (features).

   * - :math:`|A|`
     - Depending on the context may be interpreted as follows:

        + If :math:`A` is a set, this denotes its cardinality, i.e., the number
          of elements in the set :math:`A`.
        + If :math:`A` is a real number, this denotes an absolute value of
          :math:`A`.

   * - :math:`\|x\|`
     - The :math:`L_2`-norm of a vector :math:`x \in \mathbb{R}^d`,

       .. math::
          \|x\| =  \sqrt{ x_1^2 + x_2^2 + \dots + x_d^2 }.

   * - :math:`\mathrm{sgn}(x)`
     - Sign function for :math:`x \in \mathbb{R}`,

       .. math::
          \mathrm{sgn}(x)=\begin{cases}
             -1, x < 0,\\
              0, x = 0,\\
              1, x > 0.
          \end{cases}

   * - :math:`x_i`
     - In the description of an algorithm, this typically denotes the
       :math:`i`-th :term:`feature vector <Feature vector>` in the training set.

   * - :math:`x'_i`
     - In the description of an algorithm, this typically denotes the
       :math:`i`-th feature vector in the inference set.

   * - :math:`y_i`
     - In the description of an algorithm, this typically denotes the
       :math:`i`-th :term:`response <Response>` in the training set.

   * - :math:`y'_i`
     - In the description of an algorithm, this typically denotes the
       :math:`i`-th response that needs to be predicted by the inference
       algorithm given the feature vector :math:`x'_i` from the inference set.
