# projet-PPE-
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include "graphics.h" /*fichier comporte les fonctions graphiques utilisés dans le console */
#include "Membre.h"//*fichier permet la gestion de membres(ajout/suppression de membres)à completer */
#include "Seance.h" /*fichier permet la gestion des séances de reservation à fin d'eviter la duplication de dates de reservations des deux equipes (à completer)*/
#include "Reservation.h" /* fichier permet l'organisation des reservations des equipes qui veulent faire une reservation de football ou de tennis  (à completer) */
#include "Planning.h"/*fichier  permet la gestion de plannings de differents equipes participés(à completer) 



void menuPrincipal()
{
	  int i=0;

  int rep = -1;
  while(rep!=4 )
  {
               
               
      //rep1=setMenu("Menu Title", menuListTab, (sizeof(menuListTab)/sizeof(char*)), menuWidth(0 if autoResize));
               
      system("cls"); 
      char *menu[]={"Gestion des Membres","Gestion des Reservations", "Gestion des Seances", "Planning", "Exit"};
      rep=setMenu("Menu Principal", menu, (sizeof(menu)/sizeof(char*)), 10);
      switch(rep)
      {
          case 0:
          {          int rep1=-1;
                      while(rep1!=3)
                      {    
                          char *menuMembres[]={"Ajouter ", "Supprimer ", "Afficher tous les Membres", "Exit"};
                          rep1=setMenu("Gestion des Membres", menuMembres, (sizeof(menuMembres)/sizeof(char*)), 52);
                      		
                          switch(rep1)
                          {
                                       case 0:{Membre_Ajout();i++;}break;
                                       case 1:{Membre_Supprimer();i++;}break;
                                       case 2:{Membre_Affiche();}break;
                          }

                      
					  }
                      
             break;
          }
          case 1:
          {
                      int rep1=-1;
                      while(rep1!=4)
                      {    
                          char *MenuReservation[]={"Ajouter ", "Modifier ", "Supprimer ", "Consulter tous les Reservations", "Exit"};
                          rep1=setMenu("Gestion des reservations", MenuReservation, (sizeof(MenuReservation)/sizeof(char*)), 52);
                          switch(rep1)
                          {
                          	case 0:{Reservation_Ajout();
								break;
							  }
							  case 1:{Reservation_Modifier();
								break;
							  }
                          	case 2:{Reservation_Supprimer();
								break;}
                          	case 3:{Reservation_Affiche();
								break;
							  }							  
                          }
                      
					  }
                      
             break;
          }
          case 2:
          {
                      int rep1=-1;
                      while(rep1!=3)
                      {    
                          char *menuRente[]={"Ajouter", "Supprimer", "Consulter tous les Seances", "Exit"};
                          rep1=setMenu("Gestion des Seances", menuRente, (sizeof(menuRente)/sizeof(char*)), 12);
                      
                          switch(rep1)
                          {
                          	
							  case 0:{Seance_Ajout();break;
							  }

							  case 1:{Seance_Supprimer();break;
							  }                          	

                          	
							  case 2:{Seance_Affiche();break;
							  }

                          }
                      
                      
					  }
             break;
          }
          case 3:
          {
                      int rep1=-1;
                      while(rep1!=2)
                      {    
                          char *menuHelp[]={"Calendrier Football", "Calendrier Tennis", "Exit"};
                          rep1=setMenu("Planning", menuHelp, (sizeof(menuHelp)/sizeof(char*)), 12);
                          switch(rep1)
                          {
                          	  case 0:{Planning_FootballAffiche();break;
							  }
								case 1: {Planning_TennisAffiche();
									break;
								}
                          	
                                        }
                      
                      
					  }
             break;
          }
      }
      
  }
}



int main()
{
    
    menuPrincipal();
	setColor(7, 0);
    return 0;
}
