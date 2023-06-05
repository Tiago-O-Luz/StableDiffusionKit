# Stable Diffusion
Este repositorio contem um notebook exemplo para rodar Stable Diffusion 1.4 em uma GPU com 6GB de VRAM e um notebook para utilizar dentro do google collab. Mais informações no [PDF](Stable_Diffusion_INFO.pdf) disponibilizado

![](images/fantasy_landscape.png) 

Os notebooks podem ser executados sem outras dependências.

[<img src="images/download_button.webp" alt="download" width="200">](https://github.com/Tiago-O-Luz/StableDiffusionKit/archive/refs/heads/main.zip)

## Stable Diffusion Example

Notebook exemplificando uma implementação simples de stable diffusion

![](images/stable_diffusion_example.png) 

## Stable Diffusion Collab

Notebook para uso de txt2img no google collab

![](images/stable_diffusion_collab.png)

## AUTOMATIC1111 Collab

Notebook para rodar automatic 1111 pelo google collab. (Instavel sem versão paga)

# Melhorando resultados do Stable Diffusion
Esta parte está melhor explicada no pdf disponível. É recomendado sua leitura e consulta aos links encontrados lá 
## Anatomia do prompt
Para prompts pode-se dividir as palavras chaves nas seguintes categorias:

    Subject - Sujeito ou objeto principal da imagem. Quanto mais detalhes melhor será o resultado.
    Medium - Material usado para produzir imagem (Photography, Digital art, Painting)
    Style - Estilo artístico da imagem
    Artist - Usa estilo de um artista como referência
    Website - Usa resultados de um website como referência
    Resolution - Palavras chaves que ajudam a melhorar a qualidade e nitidez da imagem
    Additional details - Adjetivos e características que ajudam a especificar a imagem
    Color - Ajuda a controlar a cor das imagens que pode se manifestar nos tons da imagem ou nos objetos em si
    Lighting - Iluminação é muito importante na composição de imagens e portanto pode ter grande influência no resultado final.

## Prompt negativo
No stable diffusion é possível adicionar um prompt negativo que informa o que é indesejado na imagem. Um prompt universal que pode ser utilizado é o seguinte:

    ugly, tiling, poorly drawn hands, poorly drawn feet, poorly drawn face, out of frame, extra limbs, disfigured, deformed, body out of frame, bad anatomy, watermark, signature, cut off, low contrast, underexposed, overexposed, bad art, beginner, amateur, distorted face, blurry, draft, grainy, title, text

## Peso nas palavras chaves
O peso de uma palavra no prompt pode ser ajustado com a seguinte sintaxe: (keyword:factor). Uma sintaxe alternativa é simplesmente utilizar parênteses que aumentam por uma fator de 1.1 ou colchetes que diminuem por um fator de 0.9. Esses fatores são cumulativos da seguinte forma:
<table border="1">
 <tr>
    <td>    
(keyword) = (keyword:1.1)    

((keyword)) = (keyword:1.21)

(((keyword))) = (keyword:1.33)</td>
    <td>
[keyword] = (keyword:0.9)

[[keyword]] = (keyword:0.81)

[[[keyword]]] = (keyword:0.73)
</td>
 </tr>
</table>

## Modelo utilizado
Por se tratar de uma modelo open-source, a comunidade do Stable Diffusion criou centenas de modelos personalizados. Estes possuem forte influência nos resultados obtidos por um prompt e podem ajudar muito quando se procura gerar um tipo específico de imagem (disney, anime, hq, pintura, fotografia, etc.). Dois sites que podem ser visitados para encontrar modelos são o [hugging face](https://huggingface.co/models?other=stable-diffusion) e o [civtai](https://civitai.com).

## Sampler
Os samples determinam o ruído em cada steps da geração e portanto influenciam fortemente no resultado final.
![](images/samplers_compared.jpg)
