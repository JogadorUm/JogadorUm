import turtle

# Função para desenhar a árvore
def desenhar_arvore(tamanho, t, galho_length):
    if tamanho < galho_length:
        return
    else:
        t.forward(tamanho)
        t.left(30)
        desenhar_arvore(tamanho - galho_length, t, galho_length)
        t.right(60)
        desenhar_arvore(tamanho - galho_length, t, galho_length)
        t.left(30)
        t.backward(tamanho)

# Configurações iniciais da tartaruga
t = turtle.Turtle()
screen = turtle.Screen()
screen.bgcolor("white")
t.color("green")
t.width(2)
t.speed(10)

# Posiciona a tartaruga e desenha a árvore
t.left(90)
t.up()
t.backward(150)
t.down()
desenhar_arvore(100, t, 10)  # Galho mínimo definido como 10

# Aguarda o clique do usuário para finalizar
screen.exitonclick()
