Quinta-feira, 31 de agosto.

Passei boa parte do dia estudando estatística, mas já estou de volta ao que importa.

Terça feira, 5 de setembro.

Algumas coisas com o modelo:
- optim não funciona bem com nls ou nll, por causa dos mínimos locais.
- Com bayesian optimization, funciona muito melhor.
	- Mostrar como isso ocorre
- Tentar com preditores climáticos.

Aprendi com o Hossein a escrever e organizar melhor um script em Python. Me sinto muito mais pronta pra fazer o doutorado direito.

- organizar e comentar o código em R
- organizar e comentar o código em Python
- correr o código com os preditores climáticos.

Oops. Então, parece que o que o ax faz melhor é que força a estabelecer limites. Quando os limites são estabelecidos em R, ele converge pro valor verdadeiro.

Bom testar o que acontece com ax quando eu coloco limites maiores pros parametros.

Comparando os limites da Heinrich, parece que ela ficou presa em local minima:

model_CR_0
Nonlinear regression model
  model: Corrected_AGB ~ 133 * (1 - exp(-theta2 * age))^theta3
   data: mcwd_0
 theta2  theta3 
0.02992 1.11620 
 residual sum-of-squares: 2695
$par
         A        age      theta 
87.0759131  0.0743969  1.6919431 

$value
[1] 2612.005

model_CR_180
Nonlinear regression model
  model: Corrected_AGB ~ 119 * (1 - exp(-theta2 * age))^theta3
   data: mcwd_180
 theta2  theta3 
0.02766 1.02515 
 residual sum-of-squares: 2002
 ##########################
 $par
         A        age      theta 
66.2894298  0.1204091  2.4261043 

$value
[1] 1642.349

# model_CR_277
Nonlinear regression model
  model: Corrected_AGB ~ 96 * (1 - exp(-theta2 * age))^theta3
   data: mcwd_277
theta2 theta3 
0.0244 0.8920 
 residual sum-of-squares: 362.4
 ############################
 $par
          A         age       theta 
60.27255956  0.07430414  1.36809748 

$value
[1] 290.5912

model_CR_350
Nonlinear regression model
  model: Corrected_AGB ~ 88.5 * (1 - exp(-theta2 * age))^theta3
   data: mcwd_350
theta2 theta3 
0.0162 0.8019 
 residual sum-of-squares: 379.9
$par
          A         age       theta 
42.16826053  0.09914046  1.60265155 

$value
[1] 279.3986

water deficit strata vs agbd/age
![[Screenshot 2023-09-05 155256.png]]

![[Screenshot 2023-09-05 170257.png]]

![[Screenshot 2023-09-05 192100.png]]

![[Screenshot 2023-09-05 192712.png]]

biomass per cwd value. cwd isn't correct here.
![[Screenshot 2023-09-06 115517.png]]