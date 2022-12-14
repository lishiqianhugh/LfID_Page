<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [ ['$','$'], ["\\(","\\)"] ],
      processEscapes: true
    }
  });
</script>

![introduction](figures/introduction.jpg)

<hr>

<h2 style="text-align: center"> Abstract </h2>

<div class="gap-10"></div>

Is dynamics prediction indispensable for physical reasoning? If so, what kind of roles do the dynamics prediction modules play during the physical reasoning process? Most studies focus on designing dynamics prediction networks and treating physical reasoning as a downstream task without investigating the questions above, taking for granted that the designed dynamics prediction would undoubtedly help the reasoning process. In this work, we take a closer look at this assumption, exploring this fundamental hypothesis by comparing two learning mechanisms: Learning from Dynamics (LfD) and Learning from Intuition (LfI). 

In the **first experiment**, we directly examine and compare these two mechanisms. Results show a surprising finding: Simple LfI is better than or on par with state-of-the-art LfD. This observation leads to the **second experiment** with Ground-truth Dynamics (GD), the ideal case of LfD wherein dynamics are obtained directly from a simulator. Results show that dynamics, if directly given instead of approximated, would achieve much higher performance than LfI alone on physical reasoning; this essentially serves as the performance upper bound. Yet practically, LfD mechanism can only predict Approximate Dynamics (AD) using dynamics learning modules that mimic the physical laws, making the following downstream physical reasoning modules degenerate into the LfI paradigm; see the **third experiment**. We note that this issue is hard to mitigate, as dynamics prediction errors inevitably accumulate in the long horizon. Finally, in the **fourth experiment**, we note that LfI, the extremely simpler strategy when done right, is more effective in learning to solve physical reasoning problems. Taken together, the results on the challenging benchmark of PHYRE show that LfI is, if not better, as good as LfD with bells and whistles for dynamics prediction. However, the potential improvement from LfD, though challenging, remains lucrative.

<hr>

<h2 style="text-align: center"> Problem Definition </h2>

<div class="gap-10"></div>

### Learning from Intuition (LfI)
Directly learn the final outcome $y$ from intial images and actions by a task-solution model $f$.

$$P(y|X_0) = f(X_0;\theta)$$

### Learning from Dynamics (LfD)
Predict dynamics $D = \\{X_t | t = 0, 1, \ldots, T\\}$ by a dynamics prediction model $g$ first.

$$P(y|X_0) = f(D;\theta)$$

$$D = g(X_0;\phi)$$

<hr>

<h2 style="text-align: center"> Experiments </h2>

<div class="gap-10"></div>

* **Exp 1 - LfD vs. LfI**: An interesting finding that a binary-classification model outperforms SOTA dynamics-based model.
* **Exp 2 - LfD under GD**: Do ground-truth dynamics help make better decisions than intuition?
* **Exp 3 - LfD under AD**: How do approximate dynamics perform?
* **Exp 4 - More on LfI**: How does LfI perform?

<hr>

<h2 style="text-align: center"> Bibtex </h2>

> @inproceedings{li2022on,
>
>   title={On the Learning Mechanisms in Physical Reasoning},
> 
>   author={Li, Shiqian and Wu, Kewen and Zhang, Chi and Zhu, Yixin},
> 
>   booktitle={NeurIPS},
> 
>   year={2022}
> 
> }

<div class="gap-10"></div>
