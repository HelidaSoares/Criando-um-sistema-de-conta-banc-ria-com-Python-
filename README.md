# Criando-um-sistema-de-conta-bancaria-com-Python-
class ContaBancaria:
    def __init__(self, numero_conta, titular, saldo_inicial=0):
        self.numero_conta = numero_conta
        self.titular = titular
        self.saldo = saldo_inicial
    
    def __str__(self):
        return f"Conta: {self.numero_conta}, Titular: {self.titular}, Saldo: {self.saldo}"

class Banco:
    def __init__(self):
        self.contas = {}
    
    def criar_conta(self, numero_conta, titular, saldo_inicial=0):
        if numero_conta in self.contas:
            raise ValueError("Número de conta já existente.")
        self.contas[numero_conta] = ContaBancaria(numero_conta, titular, saldo_inicial)
        return self.contas[numero_conta]
    
    def obter_conta(self, numero_conta):
        return self.contas.get(numero_conta, None)
