from os import system
import time
system("clear")

Cedula = 1065862484
Nombre = "kevin"
compraF1 = 0
compraF2 = 0
compraF3 = 0
compraF4 = 0

precios_nuevo_toyota = {2019:2000000,2020:40000000,2021:2330000,2022:5999990}
precios_nuevo_ferrary= {2019:1000000,2020:25000000,2021:2340000,2022:5299990}
precios_nuevo_lambor = {2019:1500000,2020:36000000,2021:2330000,2022:5999990}
precios_nuevo_bmw = {2019:2000000,2020:40000000,2021:2330000,2022:5999990}
precios_nuevo_honda = {2019:2013000,2020:40005000,2021:2333300,2022:5999990}
precios_nuevo_ford = {2019:2000000,2020:40000000,2021:2330000,2022:5999990}

cliente = {}

auto_usadolista = ["TOYOTA","FERRARY","LAMBOR","BMW","FORD","HONDA"]
"""
print("Auto usado disponibles = TOYOTA")
print("Auto usado disponibles = FERRARY")
print("Auto usado disponibles = LAMBOR")
print("Auto usado disponibles = BMW")
print("Auto usado disponibles = FORD")
print("Auto usado disponibles = HONDA")
"""

registro_autousado = {}
registro_autonuevo = {}
registro_materialesAdicionales = {}
registro_mejoras_AutoNuevo = {}
registro_mejoras_AutoUsado = {}

materiales_adicionales = {"funda":10000, "pintura":40000, "llanta":20000, "kid herramientas":120000, "bateria" :200000 }
"""
print("Adicionales disponibles = funda")
print("Adicionales disponibles = pintura")
print("Adicionales disponibles = llanta")
print("Adicionales disponibles = kid herramaientas")
print("Adicionales disponibles = bateria")
"""

mejoras_nuevos = {}
mejoras_usados = {}

def Iniciar_secion():
    while True:
        try:
            Cedula = int(input("Digite su numero de documento: "))
            if Cedula == 1065862484:
                print("Cedula correctamente")
                break
        except:
            print("ERROR = Intentelo nuevamente")

    while True:
        try:
            Nombre = str(input("Ingrese su nombre de usuario: "))
            if Nombre == "kevin":
                print("Usuario correctamente")
                break
        except:
            print("ERROR = Intentelo nuevamente")
    return

def Compra_de_autos(compraF1,compraF2,compraF3,compraF4):
    while True:
        print("|-----------------------------------------------|")
        print("|--------------BIENVENIDO AL MENU---------------|")
        print("|-----------------------------------------------|")
        print("|--------------(1).AUTOS USADOS-----------------|")
        print("|--------------(2).AUTOS NUEVOS-----------------|")
        print("|--------------(3).OPCIONES DE VEHICULO---------|")
        print("|--------------(4).OPCIONES ADICIONALES---------|")
        print("|--------------(5).SALIR------------------------|")
        print("|-----------------------------------------------|\n")

        while True:
            try:
                print("-------------------------------------")
                Opc = int(input("Elija  la opción del menu:"))
                print("-------------------------------------")
                break
            except:
                print("Solo se aceptan digitos")
                
        if Opc == 1:
            menu_auto_usados(compraF1,compraF2,compraF3,compraF4)
        elif Opc == 2:
            menu_auto_nuevos(compraF1,compraF2,compraF3,compraF4)
        elif Opc == 3:
            opcion_vehiculo(compraF1,compraF2,compraF3,compraF4)
        elif Opc == 4:
            opciones_adicionales(compraF1,compraF2,compraF3,compraF4)
        elif Opc == 5:
            print("FIN DEL PROGRAMA")
            exit()

def menu_auto_usados(compraF1,compraF2,compraF3,compraF4):
    compraF1 = 0
    time.sleep(2)
    system ("clear")
    while True:
        try:
            print("Autos")
            for i in auto_usadolista:
                print(f"{i}")
            deseado = input ("selecione el auto que desee: ").upper()
            if deseado in auto_usadolista:
                opcion = input (f"esta seguro que desea {deseado} si/no? = ").lower()
                nom = deseado
                if opcion == "si": 
                    
                    auto_usadolista.remove(nom)
                    if ("TOYOTA"== nom):
                        registro_autousado[nom] = [200000,2019]
                        print("--------------------------------")
                        print("vehiculo agregado al carrito")
                        print("--------------------------------")
                        compraF1 += 200000
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                    elif ("FERRARY"== nom):
                        registro_autousado[nom] = [170000,2018]
                        print("--------------------------------")
                        print("vehiculo agregado al carrito")
                        print("--------------------------------")
                        compraF1 += 170000
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                    elif("LAMBOR"== nom):
                        registro_autousado[nom] = [350000,2016]
                        print("--------------------------------")
                        print("vehiculo agregado al carrito")
                        print("--------------------------------")
                        compraF1 += 350000
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                    elif("BMW"== nom):
                        registro_autousado[nom] = [450000,2015]
                        print("--------------------------------")
                        print("vehiculo agregado al carrito")
                        print("--------------------------------")
                        compraF1 += 450000
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                    elif ("HONDA" == nom):
                        registro_autousado[nom] = [450000,2015]
                        print("--------------------------------")
                        print("vehiculo agregado al carrito")
                        print("--------------------------------")
                        compraF1 += 450000
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                    elif ("FORD" == nom):
                        registro_autousado[nom] = [350000,2016]
                        print("--------------------------------")
                        print("vehiculo agregado al carrito")
                        print("--------------------------------")
                        compraF1 += 350000
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                elif opcion == "no":
                    print ("selecion de nuevo \n ")
                else:
                    print("dato incorrecto, intente de nuevo \n ")
            else:
                print("no se encuentra el carro seleccionado")
        except ValueError:
            print("se ingresan numero")
        else: 
            print(" ")
        return compraF1
        
def menu_auto_nuevos(compraF1,compraF2,compraF3,compraF4):
    compraF2 = 0
    system ("clear")
    while True:
        try:
            print("|--------------------------|")
            print("|---MENU DE AUTOS NUEVOS---|")
            print("|--------------------------|")
            print("|----------Ferrary---------|")
            print("|----------Lambor----------|")
            print("|----------BMW-------------|")
            print("|----------Ford------------|")
            print("|----------honda-----------|")
            print("|--------------------------|")
            
            opcion_marca = input("Ingrese la marca: ").upper()
            if opcion_marca == "TOYOTA":
                for i,j in precios_nuevo_toyota.items():
                    opcion_modelo = int (input (" [2019,2020,2021,2022] \n Ingresa el modelo: "))                
                    if opcion_modelo in precios_nuevo_toyota:
                        registro_autonuevo [opcion_marca] = [i,j]
                        precios_nuevo_toyota.pop(i,j)
                        print(f"Precio: {j}")
                        print("---------------------------- \n vehiculo agregado al carrito")
                        compraF2 += j
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                        break
                    else:
                        pass
                else: 
                    print("no se encuentra disponible el modelo")
            elif opcion_marca == "BMW": 
                for i, j in precios_nuevo_bmw.items():
                    opcion_modelo = int (input (" [2019,2020,2021,2022] \n Ingresa el modelo: "))
                    if  opcion_modelo in precios_nuevo_bmw:
                        registro_autonuevo [opcion_marca] = [i,j]
                        precios_nuevo_bmw.pop(i,j)
                        print(f"Precio: {j}")
                        print("---------------------------- \n vehiculo agregado al carrito")
                        compraF2 += j
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                        break
                    else:
                        pass
                else: 
                    print("no se encuentra disponible el modelo")
            elif opcion_marca == "FERRARY":
                for i, j in precios_nuevo_ferrary.items():
                    opcion_modelo = int (input (" [2019,2020,2021,2022] \n Ingresa el modelo: "))
                    if  opcion_modelo in precios_nuevo_ferrary:
                        registro_autonuevo [opcion_marca] = [i,j]
                        precios_nuevo_ferrary.pop(i,j)
                        print(f"Precio: {j}")
                        print("---------------------------- \n vehiculo agregado al carrito")
                        compraF2 += j
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                        break
                    else:
                        pass
                else: 
                    print("no se encuentra disponible el modelo")
            elif opcion_marca == "FORD":
                for i, j in precios_nuevo_ford.items():
                    opcion_modelo = int (input (" [2019,2020,2021,2022] \n Ingresa el modelo: "))
                    if  opcion_modelo in precios_nuevo_ford:
                        registro_autonuevo [opcion_marca] = [i,j]
                        precios_nuevo_ford.pop(i,j)
                        print(f"Precio: {j}")
                        print("---------------------------- \n vehiculo agregado al carrito")
                        compraF2 += j
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                        break
                    else:
                        pass
                else: 
                    print("no se encuentra disponible el modelo")
            elif opcion_marca == "HONDA":
                opcion_modelo = int (input (" [2019,2020,2021,2022] \n Ingresa el modelo: "))
                for i, j in precios_nuevo_honda.items():
                    if  opcion_modelo in precios_nuevo_honda:
                        registro_autonuevo [opcion_marca] = [i,j]
                        precios_nuevo_honda.pop(i,j)
                        print(f"Precio: {j}")
                        print("---------------------------- \n vehiculo agregado al carrito")
                        compraF2 += j
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                        break
                    else:
                        pass
                else: 
                    print("no se encuentra disponible el modelo")
            elif opcion_marca == "LAMBOR":
                for i, j in precios_nuevo_lambor.items():
                    opcion_modelo = int (input (" [2019,2020,2021,2022] \n Ingresa el modelo: "))
                    if  opcion_modelo in precios_nuevo_lambor:
                        registro_autonuevo [opcion_marca] = [i,j]
                        precios_nuevo_lambor.pop(i,j)
                        print(f"Precio: {j}")
                        print("---------------------------- \n vehiculo agregado al carrito")
                        compraF2 += j
                        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                        break
                    else:
                        pass
                else: 
                    print("no se encuentra disponible el modelo")
        except ValueError:
            print("solo se aceptan numero \n ")
        else:
            print(" ")
        return compraF2

def opcion_vehiculo(compraF1,compraF2,compraF3,compraF4):
    system ("clear")
    compraF3 = 0
    while True:
        try:
            pregunta = input ("Nota: para poder realizar la mejora en un carro necesita tenerlo en el carrito \n ¿desea realizar la mejora ? \n = ").lower()
            if pregunta == "si":
                if not registro_autonuevo and not registro_autousado:
                    print("la lista del carrito se encuentra vacia")
                else: 
                    print(registro_autonuevo)
                    print(registro_autousado)
                    pregunta1 = input("Ingrese la marca que desea mejorar: ").upper()
                    for i,j in registro_autonuevo.items():
                        if pregunta1 in registro_autonuevo:
                            time.sleep(2)
                            system ("cls")
                            print(f"El {i} tiene estas mejoras: \n ----------------------------------- \n  1) motor: cilindraje 2000cc \n mejora: 3500cc  precio: 200000000")
                            print("-------------------------------------------------------------------------")
                            print(f" 2) nuematicos: \n deportivos : 300000 \n nieve: 350000 \n radiales: 150000")
                            print("-----------------------------------------------------")
                            print(f"3) kit de admisión deportivo: \n cv 3: 878382 \n cv 5: 1756765 ")
                            print("------------------------------------------")
                            pregunta2 = int(input(f"Ingresa la opcion a mejorar: "))
                            if pregunta2 == 1:
                                print("precio: 200000000 \n mejora: 3500cc")
                                mejora = "35000cc"
                                precio = 200000000
                                compraF3 += 200000000
                                registro_mejoras_AutoNuevo[i]=[mejora,2200000000]
                                print("----------------------------------")
                                print("mejora agregada al carrito")
                                print("----------------------------------")
                                preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                            elif pregunta2 == 2:
                                elegir = int (input(f"escoja la mejora que desea realizar a los neumaticos \n 1) deportivos \n 2) nieve \n 3) radiales \n = "))
                                if elegir == 1:
                                    print("precio: 300000 \n mejora: llantas deportivas")
                                    mejora = "llantas deportivas"
                                    precio = 300000
                                    compraF3 += 300000
                                    registro_mejoras_AutoNuevo[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                                elif elegir == 2:
                                    print("precio: 300000 \n mejora: llanatas de nieve")
                                    mejora = ("llantas de nieve")  
                                    precio = 350000
                                    compraF3 += 350000
                                    registro_mejoras_AutoNuevo[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                                elif elegir == 3:
                                    print("precio:150000  \n mejora: llantas radiales")
                                    mejora = ("llantas radiales")  
                                    precio = 150000
                                    compraF3 += 150000
                                    registro_mejoras_AutoNuevo[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                            elif pregunta2 == 3:
                                elegir = int(input("Escoja la mejora que desea realizar al kid de admisión \n 1) cv 3  \n 2) cv 5 \n ="))
                                if elegir == 1:
                                    print("precio: 878382 \n mejora: cv 3 ")
                                    mejora = "Cv 3"
                                    precio = 878382 
                                    compraF3 += 878382 
                                    registro_mejoras_AutoNuevo[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                                elif elegir == 2:
                                    print("precio:1756765  \n mejora: cv 5 ")
                                    mejora = "Cv 5"
                                    precio = 1756765
                                    compraF3 += 1756765
                                    registro_mejoras_AutoNuevo[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                                preguntaFinal(compraF1,compraF2,compraF3,compraF4)                            
                            else:
                                print("dato no valido, ingrese de nuevo")
                        else:
                                print("El carro no se encuentra en el carrito")
                    for i, j in registro_autousado.items():
                        if pregunta1 in registro_autousado:
                            time.sleep(3)
                            system ("cls")
                            print(f"El {i} tiene estas mejoras: \n ----------------------------------- \n  1) motor: cilindraje 2000cc \n mejora: 3500cc  precio: 200000000")
                            print("-------------------------------------------------------------------------")
                            print(f" 2) nuematicos: \n deportivos : 300000 \n nieve: 350000 \n radiales: 150000")
                            print("-----------------------------------------------------")
                            print(f"3) kit de admisión deportivo: \n cv 3: 878382 \n cv 5: 1756765 ")
                            print("------------------------------------------")
                            pregunta2 = int(input(f"Ingresa la opcion a mejorar: "))
                            if pregunta2 == 1:
                                print("precio: 200000000 \n mejora: 3500cc")
                                mejora = "35000cc"
                                precio = 200000000
                                compraF3 += 200000000
                                registro_mejoras_AutoUsado[i]=[mejora,2200000000]
                                print("----------------------------------")
                                print("mejora agregada al carrito")
                                print("----------------------------------")
                                preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                            elif pregunta2 == 2:
                                elegir = int(input(f"escoja la mejora que desea realizar a los neumaticos \n 1) deportivos \n 2) nieve \n 3) radiales \n :"))
                                if elegir == 1:
                                    print("precio: 300000 \n mejora: llantas deportivas")
                                    mejora = "llantas deportivas"
                                    precio = 300000
                                    compraF3 += 300000
                                    registro_mejoras_AutoUsado[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                                elif elegir == 2:
                                    print("precio: 300000 \n mejora: llanatas de nieve")
                                    mejora = ("llantas de nieve")  
                                    precio = 350000
                                    compraF3 += 350000
                                    registro_mejoras_AutoUsado[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                                elif elegir == 3:
                                    print("precio:150000  \n mejora: llantas radiales")
                                    mejora = ("llantas radiales")  
                                    precio = 150000
                                    compraF3 += 150000
                                    registro_mejoras_AutoUsado[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)          
                            elif pregunta2 == 3:
                                elegir = int(input("Escoja la mejora que desea realizar al kid de admisión \n 1) cv 3  \n 2) cv 5 \n = "))
                                if elegir == 1:
                                    print("precio: 878382 \n mejora: cv 3 ")
                                    mejora = "Cv 3"
                                    precio = 878382 
                                    compraF3 += 878382 
                                    registro_mejoras_AutoUsado[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                                elif elegir == 2:
                                    print("precio:1756765  \n mejora: cv 5 ")
                                    mejora = "Cv 5"
                                    precio = 1756765
                                    compraF3 += 1756765
                                    registro_mejoras_AutoUsado[i]=[mejora,precio]
                                    print("----------------------------------")
                                    print("mejora agregada al carrito")
                                    print("----------------------------------")
                                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                            else:
                                print("dato no valido, ingrese de nuevo")
                        else:
                                print("El carro no se encuentra en el carrito")
                        return compraF3        
            elif pregunta == "no":
                print("bueno")
                Compra_de_autos(compraF1,compraF2,compraF3,compraF4)
                break
            else:
                print("Dato no valido")
        except ValueError:
            print("solo números")
        else:
            print("")    

def opciones_adicionales(compraF1,compraF2,compraF3,compraF4): 
    compraF4 = 0
    system ("clear")
    while True:
        try:
            opciones =  input("Herramientas adicionales a la venta \n 1) Funda: 10000 \n 2) Pintura:40000 \n 3) Llanta: 20000 \n 4) Kid herramientas: 120000 \n 5) Bateria : 200000 \n Elija una opcion \n = " ).lower()
            for i,j in materiales_adicionales.items():
                if i in opciones: 
                    registro_materialesAdicionales[i] = j
                    materiales_adicionales.pop(i,j)
                    compraF4 += j
                    print(i, ":" ,j)
                    print("--------------------------")
                    print("articulo se agrego al carrito")
                    print("--------------------------")
                    preguntaFinal(compraF1,compraF2,compraF3,compraF4)
                    return compraF4
                else:
                    pass
        except ValueError:
            print("")
        else:
            print("herramienta no disponible")
        preguntaFinal(compraF1,compraF2,compraF3,compraF4)
        
def preguntaFinal(compraF1,compraF2,compraF3,compraF4):
    Desea = input("¿Desea finalizar la compra si/no: ")
    if Desea == "si":
        compraFinal(compraF1,compraF2,compraF3,compraF4)
    elif Desea == "no":
        Compra_de_autos(compraF1,compraF2,compraF3,compraF4)
        
def compraFinal(compraF1,compraF2,compraF3,compraF4):
    print(f"La compra final es de: {compraF1 + compraF2 + compraF3 + compraF4}")
    
if __name__ == "__main__":
    while True:
        print("|---------------------------------------|")
        print("|-------------BIENVENIDOS---------------|")
        print("|--------(1).INICIAR SECIÓN-------------|")
        print("|--------(2).COMPRA DE AUTOS------------|")
        print("|--------(3).CERRAR SECIÓN--------------|")
        print("|---------------------------------------|\n")

        while True:
            try:
                print("|-------------------------------------|")
                Opc = int(input("Ingrese una opción del menu: "))
                print("|-------------------------------------|")
                break
            except:
                print("ERROR EN EL DATO")

        if Opc == 1:
            print("|SEÑOR USUARIO DIGITE SUS DATOS \n|")
            Iniciar_secion()
            print("|USUARIO GUARDADO CON EXITO|")
            Compra_de_autos(compraF1,compraF2,compraF3,compraF4)     

        elif Opc == 2:
            print("SEÑOR USUARIO NO TE HAS REGISTRADO")
            Deseo = input("¿Deseas registrarte? = si/no: ")
            if Deseo == "si":
                Iniciar_secion()
                print("----USUARIO REGISTRADO----")
                Compra_de_autos(compraF1,compraF2,compraF3,compraF4)
            elif Deseo == "no":
                exit()
                
        elif Opc == 3:
            print("|-------------------------------------|")
            print("|------------Hasta pronto-------------|")
            print("|-------------------------------------|")
            exit()
