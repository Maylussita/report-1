def automata_termina_ab(cadena):
    """
    Autómata que acepta cadenas que terminan en 'ab'
    Estados: q0 (inicial), q1 (vio 'a'), q2 (aceptación - vio 'ab')
    """
    estado = 'q0'  # Estado inicial
    
    for simbolo in cadena:
        if estado == 'q0':
            if simbolo == 'a':
                estado = 'q1'
            elif simbolo == 'b':
                estado = 'q0'
        elif estado == 'q1':
            if simbolo == 'a':
                estado = 'q1'
            elif simbolo == 'b':
                estado = 'q2'
        elif estado == 'q2':
            if simbolo == 'a':
                estado = 'q1'
            elif simbolo == 'b':
                estado = 'q0'
    
    return estado == 'q2'  # Acepta si termina en estado q2
 
print("Aceptada")
print("ab:", automata_termina_ab("ab"))        # True
print("aab:", automata_termina_ab("aab"))      # True
print("bbbab:", automata_termina_ab("bbbab"))  # True
 
print("\nRechazada")
print("a:", automata_termina_ab("a"))          # False
print("ba:", automata_termina_ab("ba"))        # False
print("aba:", automata_termina_ab("aba"))      # False
 
