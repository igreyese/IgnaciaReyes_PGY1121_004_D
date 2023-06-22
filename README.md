# IgnaciaReyes_PGY1121_004_D
prueba n°3
"lista"
vehiculo = []

"funciones"
def grabar_vehiculo():
    tipo = input("Ingresa el tipo de vehículo: ")
    patente = input("Ingresa la patente del vehículo: ")
    marca = input("Ingresa la marca del vehículo (2-15 caracteres): ")
    if not marca_valida(marca):
        print("La marca solo debe tener entre 2 a 15 caracteres.")
        return
    precio = int(input("Ingresa el valor: "))
    if precio <= 5000000:
        print("El precio debe ser más de 5.000.000.")
        return
    multas = input("Ingresa las multas de tu vehículo (monto y fecha): ")
    fech_registro = input("Ingresa la fecha de registro: ")
    nom_dueño = input("Ingresa nombre del dueño: ")
    vehiculo.append({'tipo': tipo, 'patente': patente, 'marca': marca, 'precio': precio, 'multas': multas, 'fech_registro': fech_registro, 'nom_dueño': nom_dueño})
    print("Vehiculo guardado exitosamente")

"que la patente sea valida"
def patente_valida(patente_valida):
    if len(patente_valida) != 6:
        return False
    return True

"definimos que la marca solo debe tener entre 2 a 15 caracteres"
def marca_valida(marca):
    if len(marca) < 2 or len(marca) > 15:
        return False
    return True

def buscar_vehiculo():
    patente_buscar = input("Ingrese la patente que desea buscar: ")
    encontrado = False
    for veh in vehiculo:
        if veh['patente'] == patente_buscar:
            print("Vehiculo encontrado: ")
            print(f"Tipo:              {veh['tipo']}")
            print(f"Marca:             {veh['marca']}")
            print(f"Precio:            {veh['precio']}")
            print(f"Multas:            {veh['multas']}")
            print(f"fecha registro:    {veh['fech_registro']}")
            print(f"Nombre dueño:      {veh['nom_dueño']}")
            encontrado = True
    if not encontrado:
        print("Vehículo no encontrado.")

def certificados():
    for veh in vehiculo:
        print(f"Certificado de emisión de contaminantes para el vehículo:   {veh['patente']}. Dueño:  {veh['nom_dueño']}")
        print(f"Certificado de anotaciones vigentes para el vehículo:       {veh['patente']}. Dueño:  {veh['nom_dueño']}")
        print(f"Certificado de multas para el vehículo:                     {veh['patente']}. Dueño:  {veh['nom_dueño']}")

while True:
    print("Bienvenido a AUTO_SEGURO\nTenemos las siguientes opciones:")
    print("1: Grabar vehículo.")
    print("2: Buscar vehículo.")
    print("3: Imprimir certificados.")
    print("4: Salir del sistema.")
    opcion = int(input("Ingresa una opción:   "))
    if opcion == 1:
        grabar_vehiculo()
    elif opcion == 2:
        buscar_vehiculo()
    elif opcion == 3:
        certificados()
    elif opcion == 4:
        print("Usted desea salir del programa.")
        print("Que tengas buena tarde ¡HASTA PRONTO!")
        print("Programa de Ignacia Reyes. Versión 1.0")
        break
    else:
        print("Opción inválida, vuelva a ingresar.")
