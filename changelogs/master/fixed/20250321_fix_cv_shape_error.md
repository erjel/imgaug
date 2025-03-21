# Fix error in `arithmetic._add_scalar_to_uint8_` on Windows

On Python 3.8 tests for `_add_scalar_to_uint8_` fail for
windows due to strange behavior in `cv2.add`: For NumPy
arrays without singular dimension, a simple increment
by one results in different values across the output
array.

Fixed the issue by reshaping input array to singular 
dimensions.