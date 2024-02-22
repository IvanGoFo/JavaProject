import java.util.Scanner;


public class ProyectoJava {
    public static void main(String[] args) {


        Scanner input = new Scanner(System.in);


        String NombreJugador;
        int menu,menu2,historia,EnemigoSeleccionado,lucha,inventario,equipar;
        int ContadorNivel=1,LimiteItems=3,ContadorItemsEquipados=0;
        boolean JugadorDefensa=false;
        double dano,dano2d;


        /*======================================================================================*/
        //NIVELES
        //Esta solo para simplificar el cambiar de color a los niveles no permitidos
        String[] Nivel = {
                "1.- Bosque perdido",
                "2.- Pantano fangoso",
                "3.- Cerezos de los mil ojos",
                "4.- Bastión arcano",
                "5.- Abismo infernal I",
                "6.- Abismo infernal II",
                "7.- Trono de la noche eterna"
        };


        /*======================================================================================*/
        //COLORES TEXTO


        final String RED = "\033[31m";
        final String GREEN = "\033[32m";
        final String BLUE = "\033[34m";
        final String YELLOW = "\033[33m";
        final String RESET = "\u001B[0m";


        /*======================================================================================*/
        //ENEMIGOS


        // Lista de todos los enemigos (Usar como constante no cambiar más adelante del programa)
        // Se puede añadir un enemigo o editarlo dentro de los {}
        int[][] Enemigos = {


                //Goblin
                {/*VIDA*/10,/*DAÑO*/5,/*ARMADURA*/0},


                //Zombi errante
                {/*VIDA*/20,/*DAÑO*/8,/*ARMADURA*/0},


                //Arquero corrupto
                {/*VIDA*/20,/*DAÑO*/8,/*ARMADURA*/2},


                //Espectro arcano
                {/*VIDA*/20,/*DAÑO*/12,/*ARMADURA*/6},


                //Jinete del abismo
                {/*VIDA*/30,/*DAÑO*/15,/*ARMADURA*/6},


                //Bestia del abismo
                {/*VIDA*/50,/*DAÑO*/15,/*ARMADURA*/8},


                //Legionario de la oscuridad
                {/*VIDA*/100,/*DAÑO*/25,/*ARMADURA*/10},


                //Cazador de pesadillas
                {/*VIDA*/75,/*DAÑO*/15,/*ARMADURA*/20},


                //Esqueleto
                {/*VIDA*/75,/*DAÑO*/15,/*ARMADURA*/6},


                //Emperador de la oscuridad
                {/*VIDA*/200,/*DAÑO*/50,/*ARMADURA*/40},
        };


        // Recompensas Enemigos del modo random
        int[][] EnemigoRecompensa = {


                //Goblin
                {/*VIDA*/2,/*DAÑO*/1,/*ARMADURA*/0},


                //Zombi errante
                {/*VIDA*/3,/*DAÑO*/2,/*ARMADURA*/0},


                //Arquero corrupto
                {/*VIDA*/4,/*DAÑO*/2,/*ARMADURA*/1},


                //Espectro arcano
                {/*VIDA*/4,/*DAÑO*/4,/*ARMADURA*/2},


                //Jinete del abismo
                {/*VIDA*/8,/*DAÑO*/5,/*ARMADURA*/2},


                //Bestia del abismo
                {/*VIDA*/10,/*DAÑO*/6,/*ARMADURA*/2},


                //Legionario de la oscuridad
                {/*VIDA*/25,/*DAÑO*/10,/*ARMADURA*/4},


                //Cazador de pesadillas
                {/*VIDA*/20,/*DAÑO*/8,/*ARMADURA*/10},


                //Esqueleto
                {/*VIDA*/10,/*DAÑO*/6,/*ARMADURA*/2},


                //Emperador de la oscuridad
                {/*VIDA*/75,/*DAÑO*/25,/*ARMADURA*/12},
        };


        // Lista de todos los enemigos por sus nombres
        String[] ListaEnemigos = {
                "Goblin",
                "Zombi errante",
                "Arquero corrupto",
                "Espectro arcano",
                "Jinete del abismo",
                "Bestia del abismo",
                "Legionario de la oscuridad",
                "Cazador de pesadillas",
                "Esqueleto",
                "Emperador de la oscuridad"
        };


        // Enemigo contra el que se lucha, se llenan los valores al comenzar una pelea usando la posicion
        // del array Enemigos para elegir el enemigo
        // Es float en vez de int
        double[] EnemigoLucha = new double[3];
        /*======================================================================================*/
        //JUGADOR


        // Estadisticas base del jugador, no modificables durante el programa
        int[] JugadorConstante = {/*VIDA BASE*/20,/*DAÑO BASE*/5,/*ARMADURA BASE*/0};


        // Jugador en combate
        // Se pasan los valores que haya en el array Jugador a este al entrar en combate
        double[] JugadorLucha = new double[3];
        /*======================================================================================*/
        //ITEMS


        //
        boolean[][] EquiparItems = {
                // {Item en inventario, Item equipado}
                // Máximo de 3 Items Equipados a la vez
                {false,false}, //Item 1
                {false,false}, //Item 2
                {false,false}, //Item 3
                {false,false}, //Item 4
                {false,false}, //Item 5
                {false,false}, //Item 6
                {false,false}  //Item 7
        };


        // Lista Items por nombres
        String[][] ListaItems = {
                {"Elixir Vitalicio","Obtienes 10 puntos de vida extra"},
                {"Daga Sanguinaria","Incrementa tu daño en 5"},
                {"Incrustaciones Fijas","Incrementa tu armadura en 5"},
                {"Tridente Dominado","Incrementa tu armadura en 3, tu daño en 6 y tu vida en 9"},
                {"Orbe Curativo","Obtienes 50 puntos de vida extra"},
                {"Talismán Doloroso","Incrementa tu armadura en 12"},
                {"Fuego de Erios","Incrementa tu daño en 25"}
        };


        // Estadisticas Items
        int[][] EstadisticasItems = {
                //VIDA DAÑO ARMADURA
                {10,0,0},
                {0,5,0},
                {0,0,5},
                {9,6,3},
                {50,0,0},
                {0,0,12},
                {0,25,0},
        };


       /*======================================================================================/
       //PREPARAR COMBATE


       // Llamar combate Enemigo


           for (int i=0; i<Enemigos[Posicion Array de Enemigos].length; i++){
               EnemigoLucha[i]=Enemigos[][i];
           }


       // Llamar combate Jugador (Hay que hacer que se le añadan los items cuando hayan)


           for (int i=0; i<Jugador.length; i++){
               JugadorLucha[i]=Jugador[i];
           }


       /======================================================================================*/




        System.out.println("Tu nombre puede llegar a oírse por estas tierras, asi que dinos, ¿como te llamas?: ");
        NombreJugador=input.next();
        do {
            System.out.println("\nEscoge una opción:\n1.- ¡Inicia tu aventura!\n2.- Cambia el nombre de tu héroe.\n0.- Cerrar el programa");
            menu=input.nextInt();
            switch (menu){


                //Entra en menu2 donde podemos Elegir la accion a tomar
                case 1:


                    /*======================================================================================*/
                    //JUGADOR TEMPORAL
                    //Al salir de este menu las estadísticas del jugador vuelven al valor original


                    // Estadisticas base del jugador, se pueden modificar
                    int[] Jugador = {/*VIDA BASE*/JugadorConstante[0],/*DAÑO BASE*/JugadorConstante[1],/*ARMADURA BASE*/JugadorConstante[2]};


                    /*======================================================================================*/


                    do {
                        System.out.println("\nEscoge una opción:\n1.- Entra en el modo historia.\n2.- ¡Enfréntate a un enemigo random!\n3.- Revisa tu inventario.\n4.- Manual de instrucciones\n0.- Rendirse, como un cobarde.");
                        menu2=input.nextInt();
                        switch (menu2){


                            case 1:
                                do {
                                    System.out.println("\nEscoge el nivel al que quieres ir:");
                                    for (int i=0; i<Nivel.length; i++){
                                        if (i<=ContadorNivel-1) System.out.print(GREEN+Nivel[i]+RESET+"\n");
                                        else System.out.print(RED+"-- Nivel Bloqueado"+RESET+"\n");
                                    }
                                    System.out.println("Pulse 0 para salir del modo historia\n");
                                    historia=input.nextInt();
                                    switch (historia){


                                        //Salir modo historia
                                        case 0:
                                            break;


                                        //Seleccionar un Nivel
                                        case 1, 2, 3, 4, 5, 6, 7:


                                            if (historia<=ContadorNivel){


                                                EnemigoSeleccionado=historia-1;
                                                System.out.println("\nVas a enfrentarte contra: "+ListaEnemigos[EnemigoSeleccionado]+"\n");


                                                for (int i=0; i<Enemigos[EnemigoSeleccionado].length; i++){
                                                    EnemigoLucha[i]=Enemigos[EnemigoSeleccionado][i];
                                                }


                                                for (int i=0; i<Jugador.length; i++){
                                                    JugadorLucha[i]=Jugador[i];
                                                }


                                                /*======================================================================================*/
                                                //Sistema de Lucha Niveles


                                                do {


                                                    System.out.print(RED+ListaEnemigos[EnemigoSeleccionado]+" ");
                                                    System.out.print("( VIDA: "+EnemigoLucha[0]+"  | ");
                                                    System.out.print("DAÑO: "+EnemigoLucha[1]+"  | ");
                                                    System.out.println("ARMADURA: "+EnemigoLucha[2]+" )\n"+RESET);


                                                    System.out.print(GREEN+NombreJugador+" ");
                                                    System.out.print("( VIDA: "+JugadorLucha[0]+"  | ");
                                                    System.out.print("DAÑO: "+JugadorLucha[1]+"  | ");
                                                    System.out.println("ARMADURA: "+JugadorLucha[2]+" )"+RESET);


                                                    System.out.println("\n1.- Atacar\n2.- Defenderse\n3.- Huir");
                                                    lucha=input.nextInt();


                                                    switch (lucha){
                                                        case 1, 2:
                                                            dano=(double) JugadorLucha[1]/((EnemigoLucha[2]/25)+1);
                                                            dano2d = Math.round(dano * 100.0) / 100.0;
                                                            if (lucha==2){
                                                                dano2d=dano2d/2;
                                                                JugadorDefensa=true;
                                                                JugadorLucha[0]=JugadorLucha[0]+(Jugador[2]*2);
                                                            }
                                                            EnemigoLucha[0]= (EnemigoLucha[0]-dano2d);
                                                            System.out.println("Has hecho "+dano2d+" de daño\n");
                                                            break;
                                                        case 3:
                                                            break;
                                                        default:
                                                            System.out.println("¡No hemos reconocido eso "+NombreJugador+"!");
                                                    }


                                                    if (lucha!=3) {


                                                        dano=(double) EnemigoLucha[1]/((JugadorLucha[2]/25)+1);
                                                        dano2d = Math.round(dano * 100.0) / 100.0;


                                                        if (JugadorDefensa) {
                                                            JugadorLucha[0]=JugadorLucha[0]-(dano2d/2);
                                                            System.out.println("El enemigo ha hecho "+(dano2d/2)+" de daño \n");
                                                        }
                                                        else {
                                                            JugadorLucha[0]=JugadorLucha[0]-dano2d;
                                                            System.out.println("El enemigo ha hecho "+dano2d+" de daño \n");
                                                        }
                                                    }
                                                    JugadorDefensa=false;


                                                }while(lucha!=3 && EnemigoLucha[0]>0 && JugadorLucha[0]>0 );


                                                if (lucha==3) System.out.println("Huyendo del combate...\n");
                                                else {


                                                    System.out.print(RED+ListaEnemigos[EnemigoSeleccionado]+" ");
                                                    System.out.print("( VIDA: "+EnemigoLucha[0]+"  | ");
                                                    System.out.print("DAÑO: "+EnemigoLucha[1]+"  | ");
                                                    System.out.println("ARMADURA: "+EnemigoLucha[2]+" )\n"+RESET);


                                                    System.out.print(GREEN+NombreJugador+" ");
                                                    System.out.print("( VIDA: "+JugadorLucha[0]+"  | ");
                                                    System.out.print("DAÑO: "+JugadorLucha[1]+"  | ");
                                                    System.out.println("ARMADURA: "+JugadorLucha[2]+" )"+RESET);


                                                    if (EnemigoLucha[0]<=0) {
                                                        System.out.println("\n¡¡Has logrado derrotar al enemigo y salir victorioso!!\n");
                                                        if (ContadorNivel==historia) {
                                                            ContadorNivel++;
                                                            EquiparItems[historia-1][0]=true;
                                                            System.out.println(YELLOW+"Has encontrado "+ListaItems[historia-1][0]+RESET);
                                                        }
                                                    }
                                                    else if (JugadorLucha[0]<=0) System.out.println("\nVaya… has salido un poco desfigurado, has perdido.\n");
                                                }


                                                /*======================================================================================*/
                                            }


                                            else System.out.println("¡Aun no puedes acceder a este nivel "+NombreJugador+"!");


                                            break;


                                        //Control de errores
                                        default:
                                            System.out.println("¡No hemos reconocido eso "+NombreJugador+"!");
                                    }
                                }while (historia!=0);
                                break;


                            //Enfrenta contra un enemigo Random del Array Enemigos mediante un (int)(Math.random(0)*(Enemigos.length-1))
                            case 2:
                                EnemigoSeleccionado=(int)(Math.random()*Enemigos.length);


                                System.out.println("\nVas a enfrentarte contra: "+ListaEnemigos[EnemigoSeleccionado]);


                                for (int i=0; i<Enemigos[EnemigoSeleccionado].length; i++){
                                    EnemigoLucha[i]=Enemigos[EnemigoSeleccionado][i];
                                }


                                for (int i=0; i<Jugador.length; i++){
                                    JugadorLucha[i]=Jugador[i];
                                }


                                /*======================================================================================*/
                                //Sistema de Lucha Random


                                do {


                                    System.out.print(RED+ListaEnemigos[EnemigoSeleccionado]+" ");
                                    System.out.print("( VIDA: "+EnemigoLucha[0]+"  | ");
                                    System.out.print("DAÑO: "+EnemigoLucha[1]+"  | ");
                                    System.out.println("ARMADURA: "+EnemigoLucha[2]+" )\n"+RESET);


                                    System.out.print(GREEN+NombreJugador+" ");
                                    System.out.print("( VIDA: "+JugadorLucha[0]+"  | ");
                                    System.out.print("DAÑO: "+JugadorLucha[1]+"  | ");
                                    System.out.println("ARMADURA: "+JugadorLucha[2]+" )"+RESET);


                                    System.out.println("\n1.- Atacar.\n2.- Defenderse.\n3.- Huir del combate.");
                                    lucha=input.nextInt();


                                    switch (lucha){
                                        case 1, 2:
                                            dano=(double) JugadorLucha[1]/((EnemigoLucha[2]/25)+1);
                                            dano2d = Math.round(dano * 100.0) / 100.0;
                                            if (lucha==2){
                                                dano2d=dano2d/2;
                                                JugadorDefensa=true;
                                                JugadorLucha[0]=JugadorLucha[0]+(Jugador[2]*2);
                                            }
                                            EnemigoLucha[0]= (EnemigoLucha[0]-dano2d);
                                            System.out.println("Has hecho "+dano2d+" de daño\n");
                                            break;
                                        case 3:
                                            break;
                                        default:
                                            System.out.println("¡No hemos reconocido eso "+NombreJugador+"!");
                                    }


                                    if (lucha!=3) {


                                        dano=(double) EnemigoLucha[1]/((JugadorLucha[2]/25)+1);
                                        dano2d = Math.round(dano * 100.0) / 100.0;


                                        if (JugadorDefensa) {
                                            JugadorLucha[0]=JugadorLucha[0]-(dano2d/2);
                                            System.out.println("El enemigo ha hecho "+(dano2d/2)+" de daño \n");
                                        }
                                        else {
                                            JugadorLucha[0]=JugadorLucha[0]-dano2d;
                                            System.out.println("El enemigo ha hecho "+dano2d+" de daño \n");
                                        }
                                    }
                                    JugadorDefensa=false;


                                }while(lucha!=3 && EnemigoLucha[0]>0 && JugadorLucha[0]>0 );


                                if (lucha==3) System.out.println("Huyendo del combate...\n");
                                else {


                                    System.out.print(RED+ListaEnemigos[EnemigoSeleccionado]+" ");
                                    System.out.print("( VIDA: "+EnemigoLucha[0]+"  | ");
                                    System.out.print("DAÑO: "+EnemigoLucha[1]+"  | ");
                                    System.out.println("ARMADURA: "+EnemigoLucha[2]+" )\n"+RESET);


                                    System.out.print(GREEN+NombreJugador+" ");
                                    System.out.print("( VIDA: "+JugadorLucha[0]+"  | ");
                                    System.out.print("DAÑO: "+JugadorLucha[1]+"  | ");
                                    System.out.println("ARMADURA: "+JugadorLucha[2]+" )"+RESET);


                                    if (EnemigoLucha[0]<=0) {
                                        System.out.println("\n¡¡Has logrado derrotar al enemigo y salir victorioso!!\n");


                                        for (int i=0; i<Jugador.length; i++){
                                            Jugador[i]=Jugador[i]+EnemigoRecompensa[EnemigoSeleccionado][i];
                                        }


                                        if (EnemigoRecompensa[EnemigoSeleccionado][0]>0){
                                            System.out.println(YELLOW+"Has ganado "+EnemigoRecompensa[EnemigoSeleccionado][0]+" puntos de vida"+RESET);
                                        }
                                        if (EnemigoRecompensa[EnemigoSeleccionado][1]>0){
                                            System.out.println(YELLOW+"Has ganado "+EnemigoRecompensa[EnemigoSeleccionado][1]+" puntos de daño"+RESET);
                                        }
                                        if (EnemigoRecompensa[EnemigoSeleccionado][2]>0){
                                            System.out.println(YELLOW+"Has ganado "+EnemigoRecompensa[EnemigoSeleccionado][2]+" puntos de armadura"+RESET);
                                        }


                                    }
                                    else if (JugadorLucha[0]<=0) System.out.println("\nVaya… has salido un poco desfigurado, has perdido.\n");
                                }


                                /*======================================================================================*/


                                break;


                            case 3:
                                /*======================================================================================*/
                                //SISTEMA DE INVENTARIO
                                for (int i=0; i<EquiparItems.length; i++){
                                    if (EquiparItems[i][1]) ContadorItemsEquipados++;
                                }


                                do {
                                    System.out.print(GREEN+"\nVIDA: "+Jugador[0]+"  | ");
                                    System.out.print("DAÑO: "+Jugador[1]+"  | ");
                                    System.out.println("ARMADURA: "+Jugador[2]+RESET+"\n");


                                    for (int i=0; i<EquiparItems.length; i++){


                                        if (!EquiparItems[i][0]) {
                                            System.out.println(RED+"| Item Desconocido <???> |"+RESET);
                                        }


                                        else {


                                            if (EquiparItems[i][1]){
                                                System.out.print(GREEN+"| "+ListaItems[i][0]+": "+ListaItems[i][1]);
                                                System.out.println(" | ["+(i+1)+"]"+RESET);
                                            }


                                            else {
                                                System.out.print("| "+ListaItems[i][0]+": "+ListaItems[i][1]);
                                                System.out.println(" | ["+(i+1)+"]");
                                            }
                                        }
                                    }


                                    System.out.println("\n1.- Equipar/Desequipar Item\n0.- Salir del Inventario ");
                                    inventario=input.nextInt();


                                    switch (inventario){


                                        case 0:
                                            break;


                                        case 1:


                                            System.out.println("Introduce el ítem a equipar/desequipar, recuerda que no puedes tener más de 3 ítems equipados.");
                                            equipar=input.nextInt();


                                            if (ContadorItemsEquipados==LimiteItems && !EquiparItems[equipar-1][1]){
                                                System.out.println("¡Ya tienes 3 ítems equipados! (desequipa alguno antes de equipar otro)");
                                            }


                                            else {


                                                EquiparItems[equipar - 1][1] = !EquiparItems[equipar - 1][1];


                                                if (!EquiparItems[equipar - 1][0]) {
                                                    System.out.println("¡Aún no tienes este ítem!");
                                                }


                                                else {


                                                    if (EquiparItems[equipar - 1][1]) {
                                                        System.out.println("Equipando " + ListaItems[equipar - 1][0] + "...");
                                                        ContadorItemsEquipados++;


                                                        for (int i = 0; i < Jugador.length; i++) {
                                                            Jugador[i] = Jugador[i] + EstadisticasItems[equipar - 1][i];
                                                        }
                                                    }


                                                    else {
                                                        System.out.println("Desequipando " + ListaItems[equipar - 1][0] + "...");
                                                        ContadorItemsEquipados--;


                                                        for (int i = 0; i < Jugador.length; i++) {
                                                            Jugador[i] = Jugador[i] - EstadisticasItems[equipar - 1][i];
                                                        }
                                                    }
                                                }
                                            }
                                            break;


                                        default:
                                            System.out.println("¡No hemos reconocido eso "+NombreJugador+"!");
                                    }


                                }while (inventario!=0);


                                ContadorItemsEquipados=0;
                                break;
                            /*======================================================================================*/


                            // Manual de instrucciones
                            case 4:
                                System.out.println(BLUE+"\nMANUAL DE INSTRUCCIONES");
                                System.out.println("\n  - Sistema de Combate: El sistema de combate es relativamente simple, se basa en un sistema de turnos");
                                System.out.println("    donde primero actuas tu y despues ataca el enemigo (puedes ganar al enemigo aunque te mate si le has matado");
                                System.out.println("    en el mismo turno). El combate tiene dos acciones ataque y defensa, puedes atacar para realizar tu daño");
                                System.out.println("    (reducido ligeramente por la armadura del enemigo) sobre la vida del enemigo, al defenderte realizas la");
                                System.out.println("    mitad de tu daño y recibes la mitad ademas de curarte el doble de la armadura que tienes. Si no te ves");
                                System.out.println("    con fuerzas puedes huir del combate sin perder nada más que tu honor.");
                                System.out.println("\n  - Sistema de Inventario: Despues de superar un nivel por primera vez recibiras un item el cual puedes");
                                System.out.println("    equipar al revisar tu inventario, solo puedes tener equipados a la vez un maximo de 3 items por lo que");
                                System.out.println("    tendras que escoger sabiamente cual equipar y cual no. Ademas de equipar items al revisar tu inventario");
                                System.out.println("    podrás ver tus estadisticas.");
                                System.out.println("\n  - Modo Historia: En el modo historia formado por 7 niveles podras demostrar tu valor como héroe derrotando");
                                System.out.println("    multiples enemigos que merodean por estas tierras. Recuerda llevar los objetos adecuados para derrotar a");
                                System.out.println("    a todos los enemigos y convertirte en el héroe que siempre quisiste ser!");
                                System.out.println("\n  - Enemigo Random: Enfrentate a un enemigo aleatorio y quedate con algunas de sus estadísticas, cuanto más");
                                System.out.println("    poderoso sea mas estadísticas recibiras. ¡Ten cuidado! El enemigo mas poderoso se encuentra aquí y no en");
                                System.out.println("    en el modo historia, seras capaz de derrotarlo?"+RESET);
                                break;


                            //Abandonar Partida volver a menu principal
                            case 0:
                                break;


                            //Control de errores
                            default:
                                System.out.println("¡No hemos reconocido eso "+NombreJugador+"!");
                        }
                    }while (menu2!=0);


                    break;


                //Permite cambiar el nombre
                case 2:
                    System.out.println("Introduce el nombre de tu héroe: ");
                    NombreJugador=input.next();
                    break;


                //Cerrar programa
                case 0:
                    break;


                //Control de errores
                default:
                    System.out.println("¡No hemos reconocido eso "+NombreJugador+"!");
            }
            System.out.println();
        }while (menu!=0);


        input.close();
    }
}
