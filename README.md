# Quicksort-portugol

programa {
  funcao inicio() {
    capturarVal()
  }

  funcao capturarVal() {
    inteiro valores[3]

    escreva("Digite o primeiro valor: ")
    leia(valores[0])

    escreva("Digite o segundo valor: ")
    leia(valores[1])

    escreva("Digite o terceiro valor: ")
    leia(valores[2])

    quickSort(valores, 0, 2)

    escreva("Valores ordenados: ", valores[0], ", ", valores[1], ", ", valores[2])
  }

  funcao quickSort(inteiro vals[], inteiro esquerda, inteiro direita) {
    se (esquerda < direita) {
      inteiro pivo = ordenar(vals, esquerda, direita)

      quickSort(vals, esquerda, pivo - 1)
      quickSort(vals, pivo + 1, direita)
    }
  }

  funcao inteiro ordenar(inteiro vals[], inteiro esquerda, inteiro direita) {
    inteiro pivo = vals[direita]
    inteiro i = esquerda - 1

    para (inteiro j = esquerda; j < direita; j++) {
      se (vals[j] >= pivo) { 
        i = i + 1
        trocar(vals, i, j)
      }
    }

    trocar(vals, i + 1, direita)
    retorne i + 1
  }

  funcao trocar(inteiro vals[], inteiro i, inteiro j) {
    inteiro temp = vals[i]
    vals[i] = vals[j]
    vals[j] = temp
  }
}
