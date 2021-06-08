#include <bits/stdc++.h>
using namespace std;

# define nmax 10010

typedef struct{
    string tipo;
    string ingr;
    double preco;
} Prato;


int main(){

map<string, Prato> cardapio;

int n, m;
string lixo, nome_prato, s;
double total=0;

cin >> n;

for (int i=0; i<n; i++){

    getline(cin, lixo);

    getline(cin, nome_prato);
    getline(cin, cardapio[nome_prato].tipo);
    getline(cin, cardapio[nome_prato].ingr);
    cin >> cardapio[nome_prato].preco;

}

cout << fixed << setprecision (2);

cin >> m;

getline(cin, lixo);

for (int i=0; i<m; i++){

    getline (cin,nome_prato);

    if (cardapio.find(nome_prato) == cardapio.end()){

        cout << nome_prato << " nao esta no cardapio." << endl;

    }

    else {
        cout << nome_prato << endl;
        cout << "Tipo: " << cardapio[nome_prato].tipo << endl;
        cout << "Ingredientes: " << cardapio[nome_prato].ingr << endl;
        cout << "Preco: R$ " << cardapio[nome_prato].preco << endl;
        total += cardapio[nome_prato].preco;
    }

  cout << endl;
}

cout << "Preco total: R$ " << total << "." << endl;

return 0;
}
