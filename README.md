def evaluar_cadena(cadena):
    aceptadas = {"01", "010", "0101"}
    rechazadas = {"11100", "10", "00"}
    if cadena in aceptadas:
        return "Aceptado"
    elif cadena in rechazadas:
        return "Rechazado"
    else:
        return "No definido"
#prueba
cadenas = ["11100", "10", "00", "01", "010", "0101"]
 
for c in cadenas:
    print(f"{c}: {evaluar_cadena(c)}")
