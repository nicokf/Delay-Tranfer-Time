# Delay-Tranfer-Time

import requests

def response(url, attempts = 2):
    respuesta = []
    tries = 0
    while (tries < attempts):
        tries += 1
        for url in web:
            try:
                response = requests.get(url)
                if response.status_code == 200:
                        Fecha = response.headers["date"]
                        Tiempo = response.elapsed.microseconds/1000
                        print()
                        cadena1 = f"El Response Code para la Web {url} es: {response}"
                        cadena2 = f"La Fecha de respuesta es: {Fecha}"
                        cadena3 = f"El Tiempo de Respuesta es de {int(Tiempo)} ms"
                        cadena = [cadena1,cadena2,cadena3]
                        respuesta.append(cadena)
                if response.status_code == 400:
                    print("Verificar")
            except requests.exceptions.ConnectTimeout:
                print ("Timeout")
        return respuesta
        
def promedio(url):
    lista_time = []
    for url in web:
        r = requests.get(url)
        time = int(r.elapsed.microseconds/1000)
        lista_time.append(time)
    return lista_time

web = ["https://www.nytimes.com", "https://www.cisco.com", "https://www.tesla.com"]

lista = response(web)

for pagina in lista:
    print("\n")
    for i in pagina:
        print(i)
    print("\n")

P = promedio(web)
total = int(((P[0] + P[1] + P[2]))/3)
print(f"El promedio de Delay es: {total} ms")
print("\n")
print ("Solicitud Exitosa")       
print("\n")
