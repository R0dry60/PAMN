#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<time.h>

struct tortas{

    char tipo[90];
    int clave;
    int precio;
    int num;
};


struct tortas t;
int x;

//ap=(struct tortas*)malloc((t.num)*sizeof(struct tortas));

main(){
    int b = 1;
    t.num=0;
    struct tortas ap[500];
    int claves[20];

    while(b==1){

        int opcion;
        /*ap=(struct tortas**)malloc(sizeof(int*));
		ap[x]=(struct tortas*)malloc(sizeof(struct tortas));
        /*  NOTA: me di cuenta que al usar malloc con un contador, el apuntador, en este caso usado como arreglo,
        al parecer se recorre a la siguiente posicion automaticamente, al menos en C
        */
    opcion = menu();
    x = t.num;

    switch(opcion){

    case 99:
        b = 0;
        break;

    case 1:
        strcpy(ap[x].tipo,"Torta Cubana");
        ap[x].precio = 40;
       // ap[0][x] = &torta1;
        orden(ap);
        t.num++;
        break;

    case 2:
        strcpy(ap[x].tipo,"Torta Jamon");
        ap[x].precio = 15;
//        ap = &torta1;
        orden(ap);
        t.num++;
        break;

    case 3:
        strcpy(ap[x].tipo,"Torta Especial");
        ap[x].precio = 55;
       // ap = &torta1;
        orden(ap);
        t.num++;
        break;

    case 4:
        strcpy(ap[x].tipo,"Refresco");
        ap[x].precio = 10;
       // ap = &torta1;
        orden(ap);
        t.num++;
        break;

    default:
        printf("Opcion invalida...");
        break;
    }
    x++;
    }
//    free(ap);

}

int orden(struct tortas ord[500]){

    int i,total=0,monto,cambio;
    int mas;

    system("cls");

    printf("----------Orden---------\n");
    //Recorrer el arreglo e imprimirlo
    for(i=0; i<=t.num ;i++){
        printf("\n%s ..........%d",ord[i].tipo,ord[i].precio);
        total += ord[i].precio ;
    }
    printf("\nTotal:   %d\n",total);

    printf("\n¿Desea ordenar algo mas?");
    printf("\n1.- Si");
    printf("\n2.- No\n");
    scanf("%d",&mas);

    if(mas == 2){

        printf("\nMonto recibido? ");
        scanf("%d",&monto);
        cambio = monto-total;
        printf("\nCambio: \n \t%d \n\n GRACIAS POR SU COMPRA\n",cambio);
        ticket(ord);
        system("pause");
        t.num=0;
        system("cls");
    }
    else{

        system("cls");
    }

//free(ord);
return 0;
}


int ticket(struct tortas imp[500]){

    int i,p,total=0;
    FILE *ap;
    time_t tiempo = time(0);
    struct tm *hora = localtime(&tiempo);
    char output[50];

    ap = fopen("ticket.txt","a+");

    fprintf(ap,"\n %s","Ticket");

    strftime(output,50,"%H:%M:%S",hora);
    fprintf(ap,"\tGenerado a las: %s\n",output);

    for(i=0; i<=t.num; i++){
            total += imp[i].precio;
        fprintf(ap,"\n %s\t%d\n",imp[i].tipo,imp[i].precio);
    }
    fprintf(ap,"\ntotal: %d\n\n\n\n",total);
    fclose(ap);
}



int menu(){
    FILE *ap;

    int j,i=0,r;
    struct tortas array[50];

    ap = fopen("menu.txt","r");
    if(ap == NULL){
        printf("ERROR...");
    }
    else{
        printf("Menu Cargado...\n\n");
    }

    while(feof(ap) == NULL){
       fgets(array[i].tipo,50,ap);

    i++;
    }
    for(j=0; j<i; j++){
        printf("%s",array[j].tipo);
    }


    fclose(ap);
/*
    system("cls");
    printf("-------MENU--------");
    printf("\n1.- Torta Cubana...........$40");
    printf("\n2.- Torta Jamon............$15");
    printf("\n3.- Torta Especial.........$55");
    printf("\n4.- Refresco...............$10");
    printf("\n5.- Salir");
    */
    printf("\nElija una opcion: ");
    scanf("%d",&r);


    return r;
}
