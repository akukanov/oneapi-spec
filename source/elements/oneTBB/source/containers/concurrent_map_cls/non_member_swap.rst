===============
Non-member swap
===============

.. code:: cpp

    template <typename Key, typename T, typename Compare, typename Allocator>
    void swap( concurrent_map<Key, T, Compare, Allocator>& lhs,
               concurrent_map<Key, T, Compare, Allocator>& rhs );

Equivalent to ``lhs.swap(rhs)``.
