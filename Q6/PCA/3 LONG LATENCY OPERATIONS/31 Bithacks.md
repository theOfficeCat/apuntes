


---

## Ejemplos de optimizaciones 

```C
int
max(int a, int b)
{
	if (a > b)
		return a;
	else
		return b;
}

|
v

int
max(int a, int b)
{
	return (a&-(a>b)|b&~(-(a>b)));
}
```

```C
int
abs(int n)
{
	if (n < 0)
		return -n;
	return n;
}

|
v

int
abs(int n)
{
	a = ((a>>31)^a)-(a>>31); // -mask hace -(-1) si vale todo 1
}
```