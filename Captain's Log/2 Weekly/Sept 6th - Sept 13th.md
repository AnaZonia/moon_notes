## 13 Sept, Wednesday
Tudo certo com NLL - confirmando.
#### Objetivos para o dia:
- testar o código - ver se tá fazendo sentido
- terminar a aplicação FRQNT

Preciso melhorar o sistema de atualização de código e dados usando Github - branches, e fazer sincronizar o código sempre no Polaris e no meu próprio computador. Lembrar que Janus é compartilhada e nem sempre vai estar disponível.

$par
           A          age        theta           sd 
1.372391e+02 6.684789e-03 1.618895e-01 9.285664e+00 

$value
[1] 2654955

$counts
function gradient 
     477       NA 

$convergence
[1] 0

$message
NULL

> sum((data_reduced$agbd - G(o$par, data = data_reduced))^2)
[1] 62618695

#### Reunião semanal
- tudo certo - NLL funciona! Agora é executar com o uso de terra.


## 12 Sept, Tuesday
Acabei a primeira palestra de estatística. Acho um bom guia pra estudar no fim de semana.

Terminando alguns problemas logísticos no início do dia, e já posso voltar à modelagem.

Coding:
- Running again NLL with log-transformed data
- Investigate the values where it starts breaking.
- Organize code and data
- Incorporate new branch to test changes

Negative log likelihood with data_reduced:
$par
          A         age       theta          sd 
98.74222820  0.07273725  0.18621023 11.55545802 
$value
[1] 2710442
Least squares with data_reduced:
$par
           A          age        theta 
117.68294486   0.01924908   0.16700860 
$value
[1] 63473267

NLL(c(o_nls$par, sd = 11.55545802), data_reduced)
2688754

So, least squares is outperforming NLL.

o <- optim(c(o_nls$par, sd = 0.05), NLL, data=data_reduced)
$par
           A          age        theta           sd 
117.83486033   0.01996183   0.16782137   9.34351317 
$value
[1] 2659789

So when we input NLS values into NLL, it does even better than NLS.
$value
Now, repuffing:
[1] 2652891
           A          age        theta           sd 
2.303323e+02 2.467674e-04 1.600522e-01 9.246890e+00 
Values decrease very little, and the new minima are even farther from the real global minimum.

Maybe we need to add a bit of noise to the parameters as we repuff?
Okay - holding sd fixed may make a difference.
Maybe it's all correct, but sd is messing with it.

Conclusions of the day:
There seems to be a good RSS value when the model is run with sd constrained! No need to fix it - just constrain it a bit and it seems to find a better value than NLS.

Confirm tomorrow with a fresh mind. Organize code and get everything clear with Brian and Fiona going forward as to how to continue fitting the model.

## 8 Sept, Friday

Meeting with Andrew. Foi muito útil - algumas ideias sobre como fazer o modelo funcionar, e pensar em tirar o logaritmo natural dos dois lados da equação, e ver se isso faz diferença no encaixe dos dados.

Contacted Dana Chadwick
[critical zone science]
[Science and Applications Traceability Matrix — Surface Biology and Geology (nasa.gov)](https://sbg.jpl.nasa.gov/satm)

## Weekend menu

Preparei a literatura toda no obsidian/zotero. Trabalhos domésticos levaram um dia.

## Goals for the week

Coding:
- Running again NLL with log-transformed data
- Investigate the values where it starts breaking.
- Organize code and data
- Incorporate new branch to test changes
Data
- Investigate CWD
- Mature forest
- AET
- Soil
Writing
- read articles for journal club
- finish FRQNT app

Ongoing questions
- see what the outliers look like
- Look into errors of GEDI and ESA biomass predictions
- Look into how to compare ESA and GEDI measurements with the different scales. Make sure to check for overlaps and percentages of pixels that are covered - is there a way to do that easily with R?
- Finish expanding the area to the full Amazon
- What about pastureland being misclassified - could some of that land be early secondary forest?