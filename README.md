# encuesta

1#¿Cuál es el promedio de edad de los entrevistados?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
df['EDAD'] = pd.to_numeric(df['EDAD'], errors='coerce')
promedio_total = df['EDAD'].mean()
print(f"Promedio de edad total: {promedio_total:.2f}")

2#¿Te interesa la politica?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
columna_politica = '¿Te intereasa la politica?  -Mucho -Poco -Nada' 
df[columna_politica] = df[columna_politica].astype(str).str.strip().str.capitalize()
conteo = df[columna_politica].value_counts()
print("Respuestas a la pregunta de interés político:")
print(f"Mucho: {conteo.get('Mucho', 0)}")
print(f"Poco: {conteo.get('Poco', 0)}")
print(f"Nada: {conteo.get('Nada', 0)}")
print("\nResumen general de todas las respuestas:")
print(conteo)

3#¿Porque te interesa o no te interesa la politica?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
col = "¿Por qué te interesa o no te interesa la politica? -Me aburre -No entiendo como funciona -Me preocupa el futuro - Me gusta debatir y estar informado"
# Contadores
aburre = df[col].str.contains("me aburre").sum()
no_entiende = df[col].str.contains("no entiendo").sum()
preocupa_futuro = df[col].str.contains("me preocupa el futuro").sum()
le_gusta_debatir = df[col].str.contains("me gusta debatir y estar informado").sum()
# Mostrar resultados
print(f"Personas a las que les aburre la política: {aburre}")
print(f"Personas que no entienden cómo funciona: {no_entiende}")
print(f"Personas a las que les preocupa el futuro: {preocupa_futuro}")
print(f"Personas a las que les gusta debatir y estar informadas: {le_gusta_debatir}")
no_les_interesa = df[col].str.contains("me aburre|no entiendo").sum()
print(f"Personas que no les interesa la política: {no_les_interesa}")

4#¿ Que temas te interesan de la politica?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
col_temas = "¿Qué temas te interesan de la política? -Educación -Economía -Inclusión -Tecnología -Otros"
# Contar cuántas personas mencionaron cada tema
educacion = df[col_temas].str.contains("educacion").sum()
economia = df[col_temas].str.contains("economia").sum()
inclusion = df[col_temas].str.contains("inclusion").sum()
tecnologia = df[col_temas].str.contains("tecnologia").sum()
otros = df[col_temas].str.contains("otros").sum()
# Mostrar resultados por tema
print(f"Personas interesadas en Educación: {educacion}")
print(f"Personas interesadas en Economía: {economia}")
print(f"Personas interesadas en Inclusión: {inclusion}")
print(f"Personas interesadas en Tecnología: {tecnologia}")
print(f"Personas interesadas en Otros temas: {otros}")

5#¿Como te mantienes informado de politica?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
col_medio = "¿Cómo te mantienes informado de politica? -Redes sociales -Noticias -TV -Familia/amigos"
redes = df[col_medio].str.contains("Redes sociales").sum()
noticias = df[col_medio].str.contains("Noticias").sum()
tv = df[col_medio].str.contains("TV").sum()
familia_amigos = df[col_medio].str.contains("Familia/amigos").sum()
# Imprimir resultados
print(f"Personas que se informan a través de redes sociales: {redes}")
print(f"Personas que se informan a través de noticias: {noticias}")
print(f"Personas que se informan a través de TV: {tv}")
print(f"Personas que se informan a través de familia y/o amigos: {familia_amigos}")

6#¿ Participas en politica?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
col_participa = "¿Participas en política? -Si -No"
# Contamos las respuestas
si_participa = df[col_participa].str.contains('Si').sum()
no_participa = df[col_participa].str.contains('No').sum()
# Mostrar resultados
print(f"Personas que participan en política: {si_participa}")
print(f"Personas que NO participan en política: {no_participa}")

7#¿Te involucrarias en politica?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
col_involucrarse = "¿Te involucrarías en política? -Si -No -No estoy seguro"
# Contar respuestas
se_involucrarian = df[col_involucrarse].str.contains("SI").sum()
no_se_involucrarian = df[col_involucrarse].str.contains("NO").sum()
no_estan_seguros = df[col_involucrarse].str.contains("No estoy seguro").sum()
# Mostrar respuestas
print(f"Personas que se involucrarían en política: {se_involucrarian}")
print(f"Personas que NO se involucrarían en política: {no_se_involucrarian}")
print(f"Personas que NO están seguras: {no_estan_seguros}")

#8¿ Consideras que los jovenes deben involucrarse en politica?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
columna = '¿Consideras que los jovenes deben involucrarse en política? -Si -No'
# Contar respuestas
responden_si = df[columna].str.contains('Si').sum()
responden_no = df[columna].str.contains('No').sum()
# Mostrar resultados
print(f"Personas que consideran que los jóvenes deben involucrarse en política: {responden_si}")
print(f"Personas que NO lo consideran: {responden_no}")


9#¿ Crees que la participacion de los jovenes pueden generar cambios positivos?

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
columna = "¿Crees que la participàcion de los jovenes pueden generar cambios positivos? -Si -No -En algunos aspectos"
# Contar respuestas específicas
responden_si = df[columna].str.fullmatch("Si").sum()
responden_no = df[columna].str.fullmatch("No").sum()
responden_algunos = df[columna].str.contains("En algunos aspectos").sum()
# Mostrar resultados
print(f"Personas que creen que SÍ pueden generar cambios positivos: {responden_si}")
print(f"Personas que NO lo creen: {responden_no}")
print(f"Personas que creen que SOLO EN ALGUNOS ASPECTOS: {responden_algunos}")

9#¿Consideras que los jovenes deben involucrarse en la politica? 

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('ENCUESTAFINAL.csv')
columna = '¿Consideras que los jovenes deben involucrarse en política? -Si -No'
a_favor = df[columna].str.contains('Si').sum()
en_contra = df[columna].str.contains('No').sum()
# Calcular porcentaje
total = a_favor + en_contra
porcentaje_favor = (a_favor / total) * 100 if total > 0 else 0
porcentaje_contra = (en_contra / total) * 100 if total > 0 else 0
# Mostrar resultados
print(f"Personas que consideran necesario educar sobre política en las escuelas (aprox.): {a_favor}")
print(f"Personas que NO consideran necesario educar sobre política en las escuelas (aprox.): {en_contra}")
print(f"\nPorcentaje a favor de la educación política en las escuelas: {porcentaje_favor:.2f}%")
print(f"Porcentaje en contra de la educación política en las escuelas: {porcentaje_contra:.2f}%")
