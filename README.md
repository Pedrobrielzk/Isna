# Isna
import pandas as pd

df = pd.read_excel('Reservar.xlsx', sheet_name='Carga Online - Maio')

# Filtrar apenas quem NÃO possui data preenchida
resultado = df[df['DATA ACESSO'].isna()]

# Exibir nome e data
relatorio_final = resultado[['MOTORISTA', 'DATA ACESSO']]

relatorio_final.to_excel('relatorio_sem_acesso.xlsx', index=False)

print("Relatório gerado com sucesso!")
