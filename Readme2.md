# PROYECTO 1 DE ALGORITMOS
# Lester López Duarte
# Eliezer López García
## El siguiente proyecto se divide en dos programas, uno es sobre los datos de un triangulo y dar los datos con la formula pitagorica y el otro programa trata sobre el juego ahorcado donde el jugador ingresa una palabra y otro jugador la tendra que adivinar.
---
>Algoritmo en Pseudocodigo del Programa Triple de Pitagoras
 ```Proceso Triples_De_Pitagoras_menoresa_500
	//definimos nuestras variables que utilizaremos
    Definir limite, lado1, lado2, hipotenusa Como Entero
    limite <- 500
	
    Escribir "Triples de Pitagoras menores o iguales a ", limite, ":"
	//indicamos que lado1 es igual a 1
    lado1 = 1
	// minestras lado1 sea menor a nuestra variable limite
    mientras lado1 <= limite Hacer
		// debe de darle valor a lado2 con lado1 + 1
        lado2 = lado1 + 1
		// si el resulado de nuestra variable 2 es menor a limie
        mientras lado2 <= limite Hacer
			// el valor de hipotenusa debe de ser lado2+1
            hipotenusa = lado2 + 1
			// evaluamo hipotenusa que sea menor a limite 
            mientras hipotenusa <= limite Hacer
				//agregamos una condición donde comparara la suma de los cuadrados de los dos lados y el resultado hipotenusa al cuadrado
                Si lado1^2 + lado2^2 = hipotenusa^2 Entonces
					// si la condicion se cumple nos va Imprimir  el triple de pitagoras
                    Escribir "Lado1: ", lado1, ", Lado2: ", lado2, ", Hipotenusa: ", hipotenusa
                FinSi
				// acá indicamos que los valore deben ir aumentando de uno en uno.
                hipotenusa = hipotenusa + 1
            FinMientras
            lado2 = lado2 + 1
        FinMientras
        lado1 = lado1 + 1
    FinMientras
	//indicamos un mensaje cuando el programa alla terminado
    Escribir "Estos son los resultados encontrados. Gracias."
FinProceso
  ```
---
---
>Algoritmo en C++ del Programa Triple de Pitagoras
 ```C++
 //Calculador de triple de pitagoras menores o iguales a 500
#include <iostream>
using namespace std;
int main() {
    //Variable limite en este caso hasta 500
    int limite = 500;
    //Imprimimos en pantalla el mensaje donde el usuario visualice el limite que tiene para generar las triples de pitagoras
    cout << "Triples de Pitagoras menores o iguales a " << limite << ":" << endl;
    // usamos un for en lado 1 que comience con valor "1" y le indicamos que si lado1 es menor o igual a nuetra variable limite osea "500"
    // que que aumente de 1 en 1   
    for (int lado1 = 1; lado1 <= limite; lado1++) {
        // anidamos un segundo for que nos va servir para el lado 2 el cual va comenzar con el valor de "lado1 + 1", para que lado 1 y lado 2
        // no sean iguales
        for (int lado2 = lado1 + 1; lado2 <= limite; lado2++) {
            //acá indicamos que el valor de la hipotenusa, es lado2 + 1; para compararlo con la suma de los lados
            for (int hipotenusa = lado2 +1; hipotenusa <= limite; hipotenusa++) {
                //aquí es donde comparamos la suma de los 2 lados sea igual al cuadrado de hipotenusa es decir hipotenusa por hipotenusa
                if (lado1 * lado1 + lado2 * lado2 == hipotenusa * hipotenusa ) {
                    // si se cumple la condición imprimimos el mensaje en pantalla del resultado encontrado,
                    cout << "Lado1: " << lado1 << ", Lado2: " << lado2 << ", Hipotenusa: " << hipotenusa << endl;
                }
            }
        }
    }
    // indicamos al usuario cuando allá terminado el calculo de la de los triples de pitagoras
    cout <<"Estos fueron los resultados encontrados Gracias."<< endl;

    return 0;
}
 ```
 ---
---
 >Algoritmo en Python del Programa Triple de Pitagoras
 ```Python
 # Calculador de triples de Pitágoras menores o iguales a 500
limite = 500

# Imprimimos un mensaje donde el usuario ve el límite para generar los triples de Pitágoras
print("Triples de Pitagoras menores o iguales a", limite, ":")

# Usamos un for para lado1 que comience con el valor "1" y aumente de 1 en 1 hasta el límite (500)
for lado1 in range(1, limite + 1):
    # Anidamos un segundo for para lado2, que comienza con el valor de "lado1 + 1", para que lado1 y lado2 no sean iguales
    for lado2 in range(lado1 + 1, limite + 1):
        # en un 3ser for Indicamos que el valor de la hipotenusa es lado2 + 1 para compararlo con la suma de los lados
        for hipotenusa in range(lado2 + 1, limite + 1):
            # en un if Comparamos si esta condición que es la suma de los cuadrados de los lados es igual al cuadrado de la hipotenusa
            if lado1**2 + lado2**2 == hipotenusa**2:
                # Si se cumple la condición, imprimimos un mensaje con los resultados encontrados
                print(f"Lado1: {lado1}, Lado2: {lado2}, Hipotenusa: {hipotenusa}")

# Indicamos al usuario que se han encontrado todos los resultados
print("Estos son los resultados encontrados. Gracias.")
 ```
 ---
---
 
>Algoritmo en Pseudocodigo del Juego Ahorcado
 ```
 Algoritmo AhorcadoJuego
	Definir incorrecto, num, x, a Como Entero
	Definir psecret, letra, vec1, vec2 Como Caracter
	Escribir "Ingrese la palabra secreta"
	Leer psecret
	num = Longitud(psecret)
	Dimension vec1[num], vec2[num]
	Para x = 1 Hasta num Con Paso 1 Hacer
		vec1(x) = Subcadena(psecret,x,x)
		vec2(x) = "_."
	FinPara
	a = 0
	Mientras a < 8 Hacer
		Para x = 1 Hasta num Con Paso 1 Hacer
			Escribir vec2(x) Sin Saltar
		FinPara
		Escribir ""
		Escribir "Ingrese una letra"
		Leer letra
		// Guardamos letra
		incorrecto = 1
		//Variable centinela porque se activa con un valor 
	    // y aqui vemos si esa letra se encuentra en el vector evaluando
	    // Si la condicion se cumple se almacena en vector2 previamente se mira si no hay letra almacenada
		Para x = 1 Hasta num Con Paso 1 Hacer
			si letra == vec1(x) Entonces
				si vec2(x) == "_." Entonces
					vec2(x) = letra
					var = var + 1
					incorrecto = 0
				FinSi
			FinSi
		FinPara
		si var == num Entonces
			Escribir "*****************************"
			Escribir "*****FELICIDADES*GANASTE*****"
			Escribir "*****************************"
			a = 9
		SiNo
			si incorrecto == 1 Entonces
				a = a + 1
			FinSi
			si a == 1 Entonces
				Escribir "  +-----------+"
				Escribir "  |           |"
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "=================="
				Escribir "Te quedan 7 intentos "
			FinSi
			si a == 2 Entonces
				Escribir "  +-----------+"
				Escribir "  |           |"
				Escribir "  |           O"
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "=================="
				Escribir "Te quedan 6 intentos "
			FinSi
			si a == 3 Entonces
				Escribir "  +-----------+"
				Escribir "  |           |"
				Escribir "  |           O"
				Escribir "  |           |"
				Escribir "  |           |"
				Escribir "  |           |"
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "=================="
				Escribir "Te quedan 5 intentos "
			FinSi
			si a == 4 Entonces
				Escribir "  +-----------+"
				Escribir "  |           |"
				Escribir "  |           O /"
				Escribir "  |           |/"
				Escribir "  |           |"
				Escribir "  |           |"
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "=================="
				Escribir "Te quedan 4 intentos "
			FinSi
			si a == 5 Entonces
				Escribir "  +-----------+"
				Escribir "  |           |"
				Escribir "  |         \ O /"
				Escribir "  |          \|/"
				Escribir "  |           |"
				Escribir "  |           |"
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "  |           "
				Escribir "=================="
				Escribir "Te quedan 3 intentos "
			FinSi
			si a == 6 Entonces
				Escribir "  +-----------+"
				Escribir "  |           |"
				Escribir "  |         \ O /"
				Escribir "  |          \|/"
				Escribir "  |           |"
				Escribir "  |           |"
				Escribir "  |            \"
				Escribir "  |             \"
				Escribir "  |           "
				Escribir "  |           "
				Escribir "=================="
				Escribir "Te quedan 2 intentos "
			FinSi
			si a == 7 Entonces
				Escribir "  +-----------+"
				Escribir "  |           |"
				Escribir "  |         \ O /"
				Escribir "  |          \|/"
				Escribir "  |           |"
				Escribir "  |           |"
				Escribir "  |          / \"
				Escribir "  |         /   \"
				Escribir "  |           "
				Escribir "  |           "
				Escribir "=================="
				Escribir "Te queda 1 intento "
			FinSi
			si a == 8 Entonces
				Escribir "  +-----------+"
				Escribir "  |***********|*****"
				Escribir "  |*********\*O*/***"
				Escribir "  |**********\|/****"
				Escribir "  |***********|*****"
				Escribir "  |***********|*****"
				Escribir "  |**********/*\****"
				Escribir "  |*********/***\***"
				Escribir "  |*****************"
				Escribir "  |*****************"
				Escribir "===================="
				Escribir "********************"
				Escribir "*****PERDISTE*******"
				Escribir "********************"
			FinSi
		FinSi
	FinMientras
FinAlgoritmo
  ```
---
---
>Algoritmo en C++ del Programa Triple de Pitagoras
 ```C++
#include<iostream>
using namespace std;

#define ARREGLO_MAX 100

// Para leer variables de texto se utiliza el operador << del objeto cin, que
// lee solo una palabra. Para leer una linea completa (es decir, incluyendo los
// espacios en blanco) se debe utilzar getline (ej, reemplazar cin>>x por
// getline(cin,x)), pero obliga a agregar un cin.ignore() si antes del getline

int main() {
	int a;
	int incorrecto;
	string letra;
	int num;
	string psecret;
	float var;
	string vec1[ARREGLO_MAX];
	string vec2[ARREGLO_MAX];
	int x;
	cout << "Ingrese la palabra secreta" << endl;
	cin >> psecret;
	num = psecret.size();
	for (x=1; x<=num; ++x) {
		vec1[x-1] = psecret.substr(x-1, x-x+1);
		vec2[x-1] = "_.";
	}
	a = 0;
	while (a<8) {
		for (x=1; x<=num; ++x) {
			cout << vec2[x-1];
		}
		cout << "" << endl;
		cout << "Ingrese una letra" << endl;
		cin >> letra;
		// Guardamos letra
		incorrecto = 1;
		// Variable centinela porque se activa con un valor 
		// y aqui vemos si esa letra se encuentra en el vector evaluando
		// Si la condicion se cumple se almacena en vector2 previamente se mira si no hay letra almacenada
		for (x=1; x<=num; ++x) {
			if (letra==vec1[x-1]) {
				if (vec2[x-1]=="_.") {
					vec2[x-1] = letra;
					var = var+1;
					incorrecto = 0;
				}
			}
		}
		if (var==num) {
			cout << "*****************************" << endl;
			cout << "*****FELICIDADES*GANASTE*****" << endl;
			cout << "*****************************" << endl;
			a = 9;
		} else {
			if (incorrecto==1) {
				a = a+1;
			}
			if (a==1) {
				cout << "  +-----------+" << endl;
				cout << "  |           |" << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "==================" << endl;
				cout << "Te quedan 7 intentos " << endl;
			}
			if (a==2) {
				cout << "  +-----------+" << endl;
				cout << "  |           |" << endl;
				cout << "  |           O" << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "==================" << endl;
				cout << "Te quedan 6 intentos " << endl;
			}
			if (a==3) {
				cout << "  +-----------+" << endl;
				cout << "  |           |" << endl;
				cout << "  |           O" << endl;
				cout << "  |           |" << endl;
				cout << "  |           |" << endl;
				cout << "  |           |" << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "==================" << endl;
				cout << "Te quedan 5 intentos " << endl;
			}
			if (a==4) {
				cout << "  +-----------+" << endl;
				cout << "  |           |" << endl;
				cout << "  |           O /" << endl;
				cout << "  |           |/" << endl;
				cout << "  |           |" << endl;
				cout << "  |           |" << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "==================" << endl;
				cout << "Te quedan 4 intentos " << endl;
			}
			if (a==5) {
				cout << "  +-----------+" << endl;
				cout << "  |           |" << endl;
				cout << "  |         \\ O /" << endl;
				cout << "  |          \\|/" << endl;
				cout << "  |           |" << endl;
				cout << "  |           |" << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "==================" << endl;
				cout << "Te quedan 3 intentos " << endl;
			}
			if (a==6) {
				cout << "  +-----------+" << endl;
				cout << "  |           |" << endl;
				cout << "  |         \\ O /" << endl;
				cout << "  |          \\|/" << endl;
				cout << "  |           |" << endl;
				cout << "  |           |" << endl;
				cout << "  |            \\" << endl;
				cout << "  |             \\" << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "==================" << endl;
				cout << "Te quedan 2 intentos " << endl;
			}
			if (a==7) {
				cout << "  +-----------+" << endl;
				cout << "  |           |" << endl;
				cout << "  |         \\ O /" << endl;
				cout << "  |          \\|/" << endl;
				cout << "  |           |" << endl;
				cout << "  |           |" << endl;
				cout << "  |          / \\" << endl;
				cout << "  |         /   \\" << endl;
				cout << "  |           " << endl;
				cout << "  |           " << endl;
				cout << "==================" << endl;
				cout << "Te queda 1 intento " << endl;
			}
			if (a==8) {
				cout << "  +-----------+" << endl;
				cout << "  |***********|*****" << endl;
				cout << "  |*********\\*O*/***" << endl;
				cout << "  |**********\\|/****" << endl;
				cout << "  |***********|*****" << endl;
				cout << "  |***********|*****" << endl;
				cout << "  |**********/*\\****" << endl;
				cout << "  |*********/***\\***" << endl;
				cout << "  |*****************" << endl;
				cout << "  |*****************" << endl;
				cout << "====================" << endl;
				cout << "********************" << endl;
				cout << "*****PERDISTE*******" << endl;
				cout << "********************" << endl;
			}
		}
	}
	return 0;
}

 ```
 ---
---
>Algoritmo en C++ del Programa Triple de Pitagoras
 ```Python
 if __name__ == '__main__':
	incorrecto = int()
	num = int()
	x = int()
	a = int()
	psecret = str()
	letra = str()
	vec1 = str()
	vec2 = str()
	var = int()
	print("Ingrese la palabra secreta")
	psecret = input()
	num = len(psecret)
	vec1 = [str() for ind0 in range(num)]
	vec2 = [str() for ind0 in range(num)]
	for x in range(1,num+1):
		vec1[x-1] = psecret[x-1:x]
		vec2[x-1] = "_."
	a = 0
	while a<8:
		for x in range(1,num+1):
			print(vec2[x-1], end="")
		print("")
		print("Ingrese una letra")
		letra = input()
		# Guardamos letra
		incorrecto = 1
		# Variable centinela porque se activa con un valor 
		# y aqui vemos si esa letra se encuentra en el vector evaluando
		# Si la condicion se cumple se almacena en vector2 previamente se mira si no hay letra almacenada
		for x in range(1,num+1):
			if letra==vec1[x-1]:
				if vec2[x-1]=="_.":
					vec2[x-1] = letra
					var = var+1
					incorrecto = 0
		if var==num:
			print("*****************************")
			print("*****FELICIDADES*GANASTE*****")
			print("*****************************")
			a = 9
		else:
			if incorrecto==1:
				a = a+1
			if a==1:
				print("  +-----------+")
				print("  |           |")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("==================")
				print("Te quedan 7 intentos ")
			if a==2:
				print("  +-----------+")
				print("  |           |")
				print("  |           O")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("==================")
				print("Te quedan 6 intentos ")
			if a==3:
				print("  +-----------+")
				print("  |           |")
				print("  |           O")
				print("  |           |")
				print("  |           |")
				print("  |           |")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("==================")
				print("Te quedan 5 intentos ")
			if a==4:
				print("  +-----------+")
				print("  |           |")
				print("  |           O /")
				print("  |           |/")
				print("  |           |")
				print("  |           |")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("==================")
				print("Te quedan 4 intentos ")
			if a==5:
				print("  +-----------+")
				print("  |           |")
				print("  |         \\ O /")
				print("  |          \\|/")
				print("  |           |")
				print("  |           |")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("  |           ")
				print("==================")
				print("Te quedan 3 intentos ")
			if a==6:
				print("  +-----------+")
				print("  |           |")
				print("  |         \\ O /")
				print("  |          \\|/")
				print("  |           |")
				print("  |           |")
				print("  |            \\")
				print("  |             \\")
				print("  |           ")
				print("  |           ")
				print("==================")
				print("Te quedan 2 intentos ")
			if a==7:
				print("  +-----------+")
				print("  |           |")
				print("  |         \\ O /")
				print("  |          \\|/")
				print("  |           |")
				print("  |           |")
				print("  |          / \\")
				print("  |         /   \\")
				print("  |           ")
				print("  |           ")
				print("==================")
				print("Te queda 1 intento ")
			if a==8:
				print("  +-----------+")
				print("  |***********|*****")
				print("  |*********\\*O*/***")
				print("  |**********\\|/****")
				print("  |***********|*****")
				print("  |***********|*****")
				print("  |**********/*\\****")
				print("  |*********/***\\***")
				print("  |*****************")
				print("  |*****************")
				print("====================")
				print("********************")
				print("*****PERDISTE*******")
				print("********************")


  ```
 ---
---
>Manual de Usuario
## Usuarios del programa de triangulo
### El siguiente programa genera datos al azar y los datos de las ecuaciones se realizan automaticamente usted solo debe iniciar el programa y disfrutr de los datos posibles del traigno con su hipotenusa tomando en cuenta la ley triple de pitagoras
## Usuarios del programa del juego ahorcado
### El siguiente programa trata en ingresar una palabra y esa palabra secreta la tendra que adivinar el siguiente jugador con un maximo de 7 oportunidades
  ---
  ---
  >Manual de Tecnico

## Usuarios del programa de triangulo
### El siguiente programa genera datos al azar y los datos de las ecuaciones se realizan automaticamente
## Usuarios del programa del juego ahorcado
### El siguiente programa trata en ingresar una palabra y esa palabra secreta la tendra que adivinar el siguiente jugador con un maximo de 7 oportunidades
  ---
  ---