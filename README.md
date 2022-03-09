# Los-del-Fondo
Un pedazo de repositorio guapísimo para los chabales
class personaje:
    def __init__(self, nombre, avatar):
        self.nombre = nombre
        self.avatar = avatar
    def saludo(self):
        print("Hola soy %s" % (self.nombre))
    def mostraravatar(self):
        print("%s" % (self.avatar), end ='')
    def getX(self):
        return self.x
    
    def getY(self):
        return self.y
        
    def setX(self, x):
        self.x = x
    
    def setY(self, y):
        self.y = y
    

class humano(personaje):
    def __init__(self, nombre, avatar):
        super().__init__(nombre, avatar)
    def saludo(self):
        print("Hola soy el %s" % (self.nombre))
    def getnombre(self):
        return(self.nombre)
    def setnombre(self, nombre):
        self.nombre = nombre

class extraterrestre(personaje):
    def __init__(self, nombre, avatar, planeta):
        super().__init__(nombre, avatar)
        self.planeta = planeta
    def saludo(self):
        print("Hola, soy un extraterrestre, vengo del planeta %s y me llamo %s" % (self.planeta, self.nombre))

class animal(personaje):
    def __init__(self, nombre, avatar):
        super().__init__(nombre, avatar)
        
class Escenario:
    def __init__(self, personajes, tam_x, tam_y):
        self.personajes=Personajes
        self.tam_x = tam_x
        self.tam_y = tam_y
    def saludoDePersonajes(self):
        for personaje in Personajes:
            personaje.saludo()
    def muestraAvatar(self):
        for personaje in Personajes:
            personaje.mostraravatar()
            print()
    def saludomostratavatar(self):
        for personaje in Personajes:
            personaje.saludo()
            personaje.mostraravatar()
            print()
        
        
    def muestraescenario(self):
        for x in range(self.tam_x):
            for y in range(self.tam_y):
                personajemostrado = False
                for personaje in self.personajes:
                    if personaje.getX() == x and personaje.getY() == y:
                        personaje.mostraravatar()
                        personajemostrado = True
                        continue
                if not personajemostrado:
                    print("#",  end = '')
            print()


humano1 = humano("Churumbel", "&")
humano1.setX(3)
humano1.setY(4)
extraterre1 = extraterrestre("Leovigildo", "$", "Saturno")
extraterre1.setX(5)
extraterre1.setY(2)
Personajes = [humano1, extraterre1]
Miescenario = Escenario(Personajes, 10, 8)
Miescenario.saludomostratavatar()
Miescenario.muestraescenario()

print(humano1.getnombre())
humano1.setnombre("joselu")
