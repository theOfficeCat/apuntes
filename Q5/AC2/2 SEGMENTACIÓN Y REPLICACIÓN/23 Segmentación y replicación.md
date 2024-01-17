Consiste en combinar tanto la segmentación ([21 Segmentación](21%20Segmentación.md)) como la replicación ([22 Replicación (paralelismo)](22%20Replicación%20(paralelismo).md)), dando una ganancia.

$$ Ganancia = \frac{t_{serie}}{t_{seg\_par}} = \frac{t_+ + t_{sum}}{\frac{t_{segmentado}}{ND}} = \frac{ND \cdot (t_p + t_{sum})}{t_p + \frac{t_{sum}}{NE}} $$