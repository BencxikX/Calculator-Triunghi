// ! Obligatoriu
#include <iostream>
#include <string>
using namespace std;

// ! Variabile globale

// * Variabile de tip boolean pentru return-ul functiilor separate corespunzatoare
bool laturiCorecte;
bool unghiuriCorecte;
bool triunghiExistent;

// * Variabile care stocheaza numere pentru verificarea existentei unghiurilor si a laturilor
float l1, l2, l3; // cele trei laturi stocate ca forma float pentru laturi numere rationale
int u1, u2, u3;   // cele trei unghiuri stocate ca forma integer pentru unghiuri numere intregi

// ! Verificare cazuri particulare

// * Variabile de tip boolean pentru return-ul functiilor de testare a cazurilor particulare de triunghiuri
bool triunghiEsteDreptunghic;    // variabila de tip boolean corespunzatoare return-ului functiei de verificare pentru conditia de triunghi dreptunghic => verificaTriunghiDreptunghic()
bool triunghiDreptunghicIsoscel; // variabila de tip boolean corespunzatoare return-ului functiei de verificare pentru triunghi dreptunghic isoscel => combinatiiTriunghiDreptunghicIsoscel()
bool triunghiDreptunghic;        // variabila de tip boolean corespunzatoare return-ului functiei de verificare pentru triunghi dreptunghic(triunghi dreptunghic neisoscel) => combinatiiTriunghiDreptunghic()
bool triunghiEchilateral;        // variabila de tip boolean corespunzatoare return-ului functiei de verificare pentru triunghi echilateral => combinatiiTriunghiEchilateral()
bool triunghiIsoscel;            // variabila de tip boolean corespunzatoare return-ului functiei de verificare pentru triunghi isoscel => combinatiiTriunghiIsoscel()

// ! Prototipuri functii separate

// * Prototipuri functii de verificare
bool verificaLaturile();
bool verificaUnghiurile();
bool verificaExistaTriunghi();
bool verificaTriunghiDreptunghic();

// * Prototipuri functii de evaluare cazuri triunghiuri
bool combinatiiTriunghiDreptunghicIsoscel();
bool combinatiiTriunghiDreptunghic();
bool combinatiiTriunghiEchilateral();
bool combinatiiTriunghiIsoscel();
void combinatiiTriunghiOarecare();

// ! Prototipul functiei care stocheaza ordinea executarii functiilor
void evalueazaTriunghi();

// * Executarea functiei de mai sus in cadrul functiei int main()
int main() {
    evalueazaTriunghi();
    return 0;
}

// ! Corpurile functiilor

// * Corpul functiei care verifica laturile
bool verificaLaturile() {
    cout << "Scrieti prima latura: \n";
    cin >> l1;
    cout << "Scrieti a doua latura: \n";
    cin >> l2;
    cout << "Scrieti a treia latura:  \n";
    cin >> l3;

    // ! Conditii laturi valide
    if ((l1 > 0) && (l2 > 0) && (l3 > 0)) {
        if ((l1 + l2 > l3) && (l1 + l3 > l2) && (l2 + l3 > l1)) {
            laturiCorecte = true;
            cout << "Laturile triunghiului exista. \n\n";
        } else {
            laturiCorecte = false;
            cout << "EVALUARE: Triunghiul nu exista. Laturile nu indeplinesc conditiile necesare. \n";
        }
    } else {
        laturiCorecte = false;
        cout << "EVALUARE: Triunghiul nu exista. Laturile nu indeplinesc conditiile necesare. \n";
    }
    return laturiCorecte;
}

// * Corpul functiei care verifica unghiurile
bool verificaUnghiurile() {
    if (laturiCorecte == true) {
        cout << "Scrieti primul unghi: \n";
        cin >> u1;
        cout << "Scrieti al doilea unghi: \n";
        cin >> u2;
        cout << "Scrieti al treilea unghi:  \n";
        cin >> u3;

        // ! Conditii unghiuri valide
        if ((u1 > 0) && (u2 > 0) && (u3 > 0)) {
            if (u1 + u2 + u3 == 180) {
                cout << "Unghiurile triunghiului exista. \n\n";
                unghiuriCorecte = true;

            } else {
                unghiuriCorecte = false;
                cout << "EVALUARE: Triunghiul nu exista.Unghiurile nu indeplinesc conditiile necesare. \n";
            }

        } else {
            unghiuriCorecte = false;
            cout << "EVALUARE: Triunghiul nu exista. Unghiurile nu indeplinesc conditiile necesare. \n";
        }
    }
    return unghiuriCorecte;
}
// * Corpul functiei care verifica valoarea de adevar ale functiilor verificaLaturile() si verificaUnghiurile() si evalueaza potentiala existenta a triunghiului
bool verificaExistaTriunghi() {

    // ! Conditii existenta triunghi
    if (laturiCorecte == true && unghiuriCorecte == true) {
        triunghiExistent = true;
        cout << "Laturile si unghiurile selectate exista. \n\n";
        cout << "------------------------ \n";
        cout << "CALCULARE \n";
        cout << "------------------------ \n\n";
    }
    return triunghiExistent;
}

// * Corpul functiei care verifica daca triunghiul este sau nu dreptunghic
bool verificaTriunghiDreptunghic() {
    if (triunghiExistent == true) {
        if (u1 == 90 || u2 == 90 || u3 == 90) {
            triunghiEsteDreptunghic = true;
        } else {
            triunghiEsteDreptunghic = false;
        }
    }
    return triunghiEsteDreptunghic;
}
// ! Corpurile functiilor cazurilor particulare de triunghi

// * Corpul functiei cazului particular triunghi dreptunghic si triunghi dreptunghic isoscel
bool combinatiiTriunghiDreptunghicIsoscel() {
    // ! Ordinea executarii functiei
    if (triunghiExistent == true) {
        if (triunghiEsteDreptunghic == true) {
            if ((l1 * l1 == l2 * l2 + l3 * l3) || (l2 * l2 == l1 * l1 + l3 * l3) || (l3 * l3 == l1 * l1 + l2 * l2)) {
                // ! Conditii triunghi dreptunghic isoscel
                if ((u1 == u2 && u2 < u3) || (u2 == u3 && u3 < u1) || (u1 == u3 && u3 < u2)) {
                    if ((l1 == l2 && l2 != l3) || (l2 == l3 && l3 != l1) || (l1 == l3 && l3 != l2)) {
                        triunghiDreptunghicIsoscel = true;
                        cout << "EVALUARE: Natura triunghiului gasita. Natura: TRIUNGHI DREPTUNGHIC ISOSCEL. \n";
                    } else {
                        triunghiEsteDreptunghic = false;
                        cout << "Triunghi dreptunghic isoscel invalid. \n\n";
                        cout << "Triunghi dreptunghic invalid. \n\n";
                    }
                } else {
                    triunghiDreptunghicIsoscel = false;
                    cout << "Triunghi dreptunghic isoscel invalid. \n\n";
                }
            } else {
                triunghiDreptunghic = false;
                cout << "Triunghi dreptunghic isoscel invalid. \n\n";
            }
        } else {
            triunghiDreptunghicIsoscel = false;
            cout << "Triunghi dreptunghic isoscel invalid. \n\n";
        }
    }
    return triunghiDreptunghicIsoscel;
}

bool combinatiiTriunghiDreptunghic() {
    // ! Ordinea executarii functiei
    if (triunghiExistent == true) {
        if (triunghiEsteDreptunghic == true) {
            // ! Conditii triunghi dreptunghic(neisoscel)
            if ((l1 * l1 == l2 * l2 + l3 * l3) || (l2 * l2 == l1 * l1 + l3 * l3) || (l3 * l3 == l1 * l1 + l2 * l2)) {
                if (triunghiDreptunghicIsoscel == false) {
                    triunghiDreptunghic = true;
                    cout << "EVALUARE: Natura triunghiului gasita. Natura: TRIUNGHI DREPTUNGHIC. \n";
                } else {
                    cout << "Triunghi dreptunghic invalid. \n\n";
                }
            } else {
                cout << "Triunghi dreptunghic invalid.\n\n";
            }
        }
    }
    return triunghiDreptunghic;
}

// * Corpul functiei cazului particular triunghi echilateral
bool combinatiiTriunghiEchilateral() {
    // ! Ordinea executarii functiei
    if (triunghiExistent == true) {
        if (triunghiEsteDreptunghic == false) {
            // ! Conditii triunghi echilateral
            if ((l1 == l2 && l2 == l3) && (u1 == u2 && u2 == u3 && u3 == 60)) {
                triunghiEchilateral = true;
                cout << "EVALUARE: Natura triunghiului gasita. Natura: TRIUNGHI ECHILATERAL. \n";
            } else {
                triunghiEchilateral = false;
                cout << "Triunghi echilateral invalid. \n\n";
            }
        }
    }
    return triunghiEchilateral;
}

// * Corpul functiei cazului particular triunghi isoscel
bool combinatiiTriunghiIsoscel() {
    // ! Ordinea executarii functiei
    if (triunghiExistent == true) {
        if (triunghiEsteDreptunghic == false) {
            if (triunghiEchilateral == false) {
                // ! Conditii triunghi isoscel
                if ((l1 == l2 && l2 != l3) || (l2 == l3 && l3 != l1) || (l1 == l3 && l3 != l2)) {
                    if ((u1 == u2 && u2 != u3) || (u2 == u3 && u3 != u1) || (u1 == u3 && u3 != u2)) {
                        triunghiIsoscel = true;
                        cout << "EVALUARE: Natura triunghiului gasita. Natura: TRIUNGHI ISOSCEL. \n";
                    }
                } else {
                    triunghiIsoscel = false;
                    cout << "Triunghi isoscel invalid. \n\n";
                }
            }
        }
    }
    return triunghiIsoscel;
}

// * Corpul functiei cazului particular triunghi oarecare
void combinatiiTriunghiOarecare() {
    // ! Ordinea executarii functiei
    if (triunghiExistent == true) {
        if (triunghiDreptunghic == false) {
            if (triunghiEchilateral == false) {
                if (triunghiIsoscel == false) {
                    // ! Conditii triunghi oarecare
                    if ((l1 != l2 && l2 != l3) && (u1 != u2 && u2 != u3)) {
                        // *Logica folosita in program este ca daca triunghiul exista, nu este dreptunghic, echilateral sau isoscel dar este valid
                        // * este oarecare
                        cout << "EVALUARE: Natura triunghiului gasita. Natura: TRIUNGHI OARECARE. \n";
                    } else {
                        triunghiExistent = false;
                        cout << "Triunghi oarecare invalid. \n\n";
                        cout << "EVALUARE: TRIUNGHIUL NU EXISTA. \n";
                    }
                }
            }
        }
    }
}

// * Corpul functiei care stocheaza ordinea efectuarii celorlalte functii individuale intr-o singura functie, apelata in int main()
void evalueazaTriunghi() {
    verificaLaturile();
    verificaUnghiurile();
    verificaExistaTriunghi();
    verificaTriunghiDreptunghic();
    combinatiiTriunghiDreptunghicIsoscel();
    combinatiiTriunghiDreptunghic();
    combinatiiTriunghiEchilateral();
    combinatiiTriunghiIsoscel();
    combinatiiTriunghiOarecare();
}
