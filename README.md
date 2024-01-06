# MultiPad Skin Template
Esta é um modelo de skin suportada exclusivamente pelo MultiPad, com intuito de ser mais fácil de criar, pois você não precisará [criar um APK para uma pele](LINK_DA_SKIN_TEMPLATE_UNIPAD) para usar no MultiPad, e também ser mais "Específico" para personalizar o máximo de detalhes do seu Launchpad virtual.
# Detalhes
## Geral
Todos os modelos de skin possuem um arquivo ["skin_info.json"](skin_info.json) que irá armazenar todas as informações necessário para que o MultiPad possa reconhecer e aplicar corretamente a skin. A estrutura do arquivo pode variar dependendo do modelo de skin, atualmente modelo [básico](#Modelo básico) e [avançado](#Modelo avançado). Todas as informações necessárias para que você possa trabalhar com as skins está logo abaixo (A estrutura de arquivos você poderá usar as amostras disponíveis neste repositório). O diretório das Skins é "/MultiPad/Skins"
## O arquivo "skin_info.json"
Este arquivo permite que o MultiPad identifique aquele diretório como uma Skin, então é obrigatório a existência deste arquivo no diretório da sua skin (Exemplo.: /MultiPad/Skins/Minha Skin Personalizada/skin_info.json). Nele, haverá as informações necessárias que o MultiPad precisa para obter o nome, autor e versão daquela determinada skin. Além dessa informações, haverá algumas outras informações que será necessário para identificação do tipo de skin.
## Modelo básico
O modelo básico funciona da mesma forma que as skins do Unipad, pois só preciso dos PNG's comuns renomeados como "chainled", "btn", "btn_", "phatom", "pahtom_", "playbg" e etc. No modelo básico, a estrutura do arquivo "skin_info.json" será na seguinte forma:
```
{
	"skin_name": "NOME_DA_SKIN",
	"skin_author": "NOME_DO_AUTOR_DA_SKIN",
	"skin_version": "VERSÃO_DA_SKIN",
	"skin_type": "basic"
}
```
## Modelo avançado
O modelo avançado de skin é para quem não tem preguiça e quer fazer a skin o mais maneiro possível, pois você poderá customizar as almofadas individualmente. A diferença do [Modelo avançado](#Modelo avançado) para o [Modelo básico](#Modelo básico) é a possibilidade de usar um .png para cada almofada, para criar skins muito específica, por exemplo um skin bem real de uma Novation Launchpad. No modelo básico, a estrutura se arquivos "skin_info.json" será na seguinte forma:
```
{
	"skin_name": "NOME_DA_SKIN",
	"skin_author": "NOME_DO_AUTOR_DA_SKIN",
	"skin_version": "VERSÃO_DA_SKIN"
	"skin_type": "advanced"
	"skin_pads": {
		"0,1": "png1.png",
		"0,2": "png2.png"
	}
}
```
Como está é uma skin mais avançada, logo será trabalhosa, então vou explicar como esta estrutura funciona:
- A variável "skin_pads" é um dicionário que deve conter `"COORDENADAS_X_Y": "NOME_DO_PNG"`, onde `"COORDENADAS_X_Y"` é as coordenadas X e Y da almofada (`"1,5", "5,9", "4,6"`, etc...) e `"NOME_DO_PNG"` é o nome do png que você quer usar nesta almofada (`"pad1.png", "custompad.png", "37.png"`, etc...)... (Sim, falei o óbvio).

Caso você esqueça de algum botão, o MultiPad irá substituir pelo PNG padrão, por exemplo:
- se você esquecer da coordenada "4,4", "4,5", "5,4" e "5,5", MultiPad usará a PNG "phatom_" presente na skin.
- se você esquecer da coordenada dos botões que não são as "Chain/CC" e as mencionadas acima, MultiPad usará a PNG "phantom" presente na skin.
- se você esquece da coordenada referente às "Chain/CC", MultiPad usará a PNG "chainled" presente na skin.
Caso alguma PNG padrão não esteja presente na skin, MultiPad irá usar a PNG da pele padrão.
Veja o "skin_info.json" para entender melhor o que estou dizendo.