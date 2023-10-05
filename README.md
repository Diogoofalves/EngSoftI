# EngSoftI
Bem-vindo ao projeto da disciplina EngSoftI!
## Descrição
Este repositório contém todos os materiais e projetos relacionados à disciplina EngSoftI.

# UNIVERSIDADE COMUNITÁRIA REGIONAL DE CHAPECÓ - UNOCHAPECÓ
## IHeal
### Objetivo:
   Este caso de uso serve para auxiliar no desenvolvimento de um aplicativo para encomenda e entrega de medicamentos, pois sempre que estou doente preciso me deslocar até a farmácia para comprar medicamento, com este aplicativo poderei ficar descansando no conforto da minha residência e receber meus remédios, assim segue os passos:
1. Um "Cliente" inicia o processo, solicitando um medicamento por meio do "Aplicativo
de Entrega".
2. O "Aplicativo de Entrega" consulta o "Banco de Dados" para verificar o estoque do
medicamento.
3. O "Banco de Dados" fornece ao "Aplicativo de Entrega" os dados do estoque.
4. O "Aplicativo de Entrega" envia um pedido à "Farmácia" para o medicamento.
5. A "Farmácia" confirma o recebimento do pedido.
6. O "Aplicativo de Entrega" atribui a entrega a um "Entregador".
7. O "Entregador" aceita a entrega.
8. O "Aplicativo de Entrega" notifica o "Cliente" de que a entrega está em andamento.
9. O "Cliente" acompanha a entrega.
10.O "Entregador" atualiza o status da entrega para o "Aplicativo de Entrega".
11.O "Aplicativo de Entrega" atualiza o status da entrega para o "Cliente".
12.O "Cliente" confirma a entrega.
13.O "Entregador" confirma a entrega para o "Aplicativo de Entrega".
14.O "Aplicativo de Entrega" confirma a entrega para o "Cliente".
### Codigo:
@startuml
!define ColorCliente #FFFFFF
!define ColorAplicativo #FF0000
!define ColorBancoDeDados #0000FF
!define ColorFarmacia #FFFF00
!define ColorEntregador #00FFFF
skinparam {
actor {
BackgroundColor ColorCliente
BorderColor Black
}
participant {
BackgroundColor ColorAplicativo
BorderColor Black

}
database {
BackgroundColor ColorBancoDeDados
BorderColor Black
}
participant {
BackgroundColor ColorFarmacia
BorderColor Black
}
participant {
BackgroundColor ColorEntregador
BorderColor Black
}
}
actor Cliente as "Cliente"
participant Aplicativo as "Aplicativo de Entrega"
database Banco_de_Dados as "Banco de Dados"
participant Farmácia as "Farmácia"
participant Entregador as "Entregador"
Cliente -> Aplicativo : Solicitar medicamento
activate Aplicativo
Aplicativo -> Banco_de_Dados : Consultar estoque
Banco_de_Dados --> Aplicativo : Dados do estoque
Aplicativo -> Farmácia : Enviar pedido
activate Farmácia
Farmácia -> Aplicativo : Confirmar recebimento do pedido
deactivate Farmácia
Aplicativo -> Entregador : Atribuir entrega
activate Entregador
Entregador -> Aplicativo : Aceitar entrega
deactivate Entregador
Aplicativo -> Cliente : Notificar entrega em andamento
Cliente -> Entregador : Acompanhar entrega
Entregador --> Aplicativo : Atualizar status da entrega
Aplicativo --> Cliente : Atualizar status da entrega
Cliente -> Entregador : Confirmar entrega
Entregador --> Aplicativo : Entrega confirmada
Aplicativo --> Cliente : Entrega confirmada
deactivate Aplicativo
@enduml
### Imagem: 
![image](https://github.com/Diogoofalves/EngSoftI/assets/147007827/06a0dddc-69a9-4c6d-9008-086362235919)
