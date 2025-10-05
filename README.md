# Desafio-war-estruturado
Trabalho Desafio war estruturado - Estácio
#include <stdio.h>
#include <string.h>

struct Territorio {
    char nome[50];
    char corExercito[20];
    int numeroTropas;
};

void limparBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    struct Territorio mapa[5];
    int i;

    printf("--- DESAFIO WAR: NÍVEL NOVATO ---\n");
    printf("Cadastro Inicial dos 5 Territórios\n\n");

    for (i = 0; i < 5; i++) {
        printf("--- Cadastrando Territorio %d ---\n", i + 1);

        printf("Digite o nome do territorio: ");
        fgets(mapa[i].nome, 50, stdin);
        mapa[i].nome[strcspn(mapa[i].nome, "\n")] = 0;

        printf("Digite a cor do exercito: ");
        fgets(mapa[i].corExercito, 20, stdin);
        mapa[i].corExercito[strcspn(mapa[i].corExercito, "\n")] = 0;

        printf("Digite o numero de tropas: ");
        scanf("%d", &mapa[i].numeroTropas);
        limparBuffer();

        printf("\n");
    }

    printf("\n--- ESTADO ATUAL DO MAPA ---\n");
    printf("--------------------------------------------------\n");
    printf("%-20s | %-15s | %s\n", "Territorio", "Cor do Exercito", "Tropas");
    printf("--------------------------------------------------\n");

    for (i = 0; i < 5; i++) {
        printf("%-20s | %-15s | %d\n",
               mapa[i].nome,
               mapa[i].corExercito,
               mapa[i].numeroTropas);
    }
    printf("--------------------------------------------------\n");

    return 0;
}
