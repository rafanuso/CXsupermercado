# Cupom de Venda em JavaScript

Este código permite cadastrar vários produtos, calcular os subtotais e mostrar o total final da compra de forma simples.

## Código

```javascript
var totalGeral = 0; // guarda o total da compra
var continuar = "s"; // controla se o usuário quer continuar

console.log("    CUPOM DA VENDA    " + 
            "\n\n-------------------- " + 
            "\n ITEM   DESCRIÇÃO" + 
            "\n\nqtd   valor    total" + 
            "\n--------------------");

var item = 1; // contador dos itens

// estrutura de repetição
while (continuar === "s") {
    var prod = prompt("Digite o produto: ");
    var preco = parseFloat(prompt("Insira o valor da unidade: ").replace(",","."));
    var qtd = parseInt(prompt("Digite a quantidade: ").replace(",","."));
    
    var subtotal = preco * qtd; // calcula o valor daquele produto
    totalGeral = totalGeral + subtotal; // acumula no total geral

    // imprime o produto no cupom
    console.log(item + "   " + prod);
    console.log(qtd + "     " + preco + "      " + subtotal.toFixed(2) + "\n--------------------");

    item++; // soma 1 ao número do item
    continuar = prompt("Deseja inserir outro produto? (s/n)"); // pergunta se continua
}

// no final mostra o total geral
console.log("\nTotal R$ " + totalGeral.toFixed(2));
