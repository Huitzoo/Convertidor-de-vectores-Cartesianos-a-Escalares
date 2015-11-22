# Convertidor-de-vectores-Cartesianos-a-Escalares
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
/*Programa para transformar de vectores en coordenadas escalares a esfericas, aplicado en un punto del espacio*/
float i, j, k;
float calcula();
float x=0, y=0, z=0, a=0, b=0, c=0, r=0, te=0, fi=0, R=0, ar=0, ate=0, afi=0, ara=0, arb=0, arc=0, atea=0, ateb=0, atec=0, afia=0, afib=0, afic=0;
int main(int argc, char *argv[])
{
  printf("\t\t\t\tConvertidor de coordenadas cartesianas a esfericas");
	printf("\n\nIngresa el vector F=(i,j,k) \n");
	printf("X= ");
	scanf("%f", &x);
	printf("\nY=");
	scanf("%f", &y);
	printf("\nZ= ");
	scanf("%f", &z);
	printf("\nIngresa las coordenadas donde se aplica la fuerza P(a,b,c): ");
	printf("\na= ");
	scanf("%f", &a);
	printf("\nb=");
	scanf("%f", &b);
	printf("\nc= ");
	scanf("%f", &c);
	calcula();
	printf("\nSu vector F(%.2f,%.2f,%.2f) en cartesianas es, F(%.3f,%.3f,%.3f) en esfericas\n", x, y, z, ar, ate, afi);
system("PAUSE");
return 0;
}
float calcula()
{
	r=sqrt((a*a)+(b*b)+(c*c));
	R=sqrt((a*a)+(b*b));
	te=acos(a/r);
	fi=asin(R/r);
	ara=((sin(fi)*cos(te))*a);
	arb=((sin(fi)*sin(te))*b);
	arc=((cos(fi))*c);
	afia=((cos(fi)*cos(te))*a);
	afib=((cos(fi)*sin(te))*b);
	afic=((-sin(fi))*c);
	atea=((-sin(fi))*a);
	ateb=((cos(te))*b);
	ar=((x*ara)+(y*arb)+(z*arc));
	ate=((x*atea)+(y*ateb)+(z*atec));
	afi=((x*afia)+(y*afib)+(z*afic));         	
}
