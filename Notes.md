### Major Notes

- Color Theme : BGR
- CV2 Dimension Pattern : width, height
- Numpy Shape : Row, Colum 

The width, height will be height,width for Numpy

### Performance Measurement and Improvement Techniques

#### Measuring Performance with OpenCV

The `cv.getTickCount` function returns the number of clock-cycles after a reference event (like the moment the machine was switched ON) to the moment this function is called. So if you call it before and after the function execution, you get the number of clock-cycles used to execute a function.


The `cv.getTickFrequency` function returns the frequency of clock-cycles, or the number of clock-cycles per second. So to find the time of execution in seconds, you can do following:

```python
    img1 = cv.imread('messi5.jpg')
    assert img1 is not None, "file could not be read, check with os.path.exists()"
    
    e1 = cv.getTickCount()
    for i in range(5,49,2):
        img1 = cv.medianBlur(img1,i)
    e2 = cv.getTickCount()
    t = (e2 - e1)/cv.getTickFrequency()
    print( t )
    
    # Result I got is 0.521107655 seconds
```

### Default Optimization in OpenCV

OpenCv by default provides optimized code. Also, it contains unoptimized code as well. So to use Optimized code we should check if our system support these features. OpenCv will run the optimized code if it is enabled. 

To check if optimization is supported or not `cv.useOptimized()
` - > `Bool`

To set the optimization ` cv.setUseOptimized(True)`


### Measuring Performance in IPython

Sometimes you may need to compare the performance of two similar operations. IPython gives you a magic command `timeit` to perform this. It runs the code several times to get more accurate results. Once again, it is suitable to measuring single lines of code.

For example, do you know which of the following addition operations is better, `x = 5; y = x**2`, `x = 5; y = x*x`, `x = np.uint8([5]); y = x*x`, or `y = np.square(x)`? We will find out with `timeit` in the IPython shell.

```python
    In [10]: x = 5
    
    In [11]: %timeit y=x**2
    10000000 loops, best of 3: 73 ns per loop
    
    In [12]: %timeit y=x*x
    10000000 loops, best of 3: 58.3 ns per loop
    
    In [15]: z = np.uint8([5])
    
    In [17]: %timeit y=z*z
    1000000 loops, best of 3: 1.25 us per loop
    
    In [19]: %timeit y=np.square(z)
    1000000 loops, best of 3: 1.16 us per loop
```