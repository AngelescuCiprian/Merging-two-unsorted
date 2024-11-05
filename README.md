/*
Interclasarea a doi vectori
fiecare vector sa fie sortat printr-o metoda diferita
(bubble sort, selectie , insertie)
v1
v2
=>v3
*/
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
void main()
{
	int n,m,i, v1[100], v2[100], j, k, v3[200],sortat,aux,aux2; //inline comment
	printf("n= ");
	scanf("%i", &n);
	printf("m= ");
	scanf("%i", &m);
	printf("Introduceti elementele primului vector :\n");
	for (i = 0; i < n; i++) {
		printf("v1[%i]=", i);
		scanf("%i", &v1[i]);
	}
	printf("Introduceti elementele celui de-al doilea vector :\n");
	for (i = 0; i < m; i++) {
		printf("v2[%i]=", i);
		scanf("%i", &v2[i]);
	}
	//Bubble sort primul v1
	do
	{
		sortat = 1;
		for (i = 0; i < n - 1; i++)
		{
			if (v1[i] > v1[i + 1])
			{
				sortat = 0;
				aux = v1[i];
				v1[i] = v1[i + 1];
				v1[i + 1] = aux;
			}
		}
	} while (!sortat);
	printf("\nPrimul vector sortat crescator : ");
	for (i = 0; i < n; i++)
		printf("%i ", v1[i]);
	//Selection sort v2
	for (i = 0; i < m - 1; i++)
	{
		for (j = i + 1; j < m; j++)
		{
			if (v2[i] > v2[j])
			{
				aux2 = v2[i];
				v2[i] = v2[j];
				v2[j] = aux2;
			}
		}
	}
	printf("\nAl doilea vector sortat crescator : ");
	for (i = 0; i < m; i++)
		printf("%i ", v2[i]);
	//Interclasare
	i = 0, j = 0,k=0;
	while (i < n && j < m)
	{
		if (v1[i] <v2[j])
		{

			v3[k] = v1[i];
			i++;
			k++;
		}
		else if(v1[i]>v2[j])
		{

			v3[k] = v2[j];
			j++;
			k++;
		}
		else
		{

			v3[k]=v2[j];
			j++;
			i++;
			k++;
		}
	}
	while (i < n)
	{

		v3[k] = v1[i];
		i++;
		k++;
	}
	while (j < m)
	{

		v3[k] = v2[j];
		j++;
		k++;
	}

	printf("\nInterclasarea vectorilor este : \n");
	for (i = 0; i < k; i++)
		printf("%i ", v3[i]);



}
