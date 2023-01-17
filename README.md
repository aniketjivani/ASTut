Finally, a working version of the basic stuff from https://github.com/paulcon/active_subspaces

Some tips:
- get it from here and try to build, https://github.com/mathematicalmichael/active_subspaces
- do something like `python setup.py build_py`
- then something like `python setup.py install_lib`
- if everything fails, take the `active_subspaces` folder and copy it to wherever you need to call functions (just lots of issues with scipy, gcc, blas_lapack and so on - this has not been well-maintained tbh, very very frustrating)
- go into `utils` and open files like `response_surfaces.py`, `domains.py`: wherever you see `from scipy.misc import comb` change that to `from scipy.special import comb`

- comment out these from `sufficient_summary` under `plotters.py` in `utils` (they mess up the heatmap):
```python
   #     plt.axis([ymin, ymax, ymin, ymax])
   #     plt.axes().set_aspect('equal')
   #     plt.grid(True)
   #     plt.title(out_label)
```
Optionally add `plt.set_cmap('jet')` to match the original Borehole tutorial figure.
