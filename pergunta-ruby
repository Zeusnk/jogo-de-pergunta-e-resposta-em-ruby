require 'gosu'

class GameWindow < Gosu::Window
  def initialize
    super(640, 480)
    self.caption = "Jogo de Perguntas e Respostas"
    @font = Gosu::Font.new(32)
    @question = "Qual é a capital do Brasil?"
    @options = ["1. São Paulo", "2. Rio de Janeiro", "3. Brasília", "4. Belo Horizonte"]
    @correct_answer = 2
    @edit_mode = false
    @edit_index = 0
  end

  def draw
    @font.draw(@question, 50, 50, 0)
    @options.each_with_index do |option, index|
      if index == @correct_answer
        color = Gosu::Color::BLACK
      else
        color = Gosu::Color::BLACK
      end
      Gosu.draw_rect(50, 100 + (index * 50), 200, 40, color)
      @font.draw(option, 60, 110 + (index * 50), 0)
    end
    if @edit_mode
      Gosu.draw_rect(400, 50 + (@edit_index * 50), 200, 40, Gosu::Color::GRAY)
      @font.draw(@options[@edit_index], 410, 60 + (@edit_index * 50), 0)
    end
  end

  def button_down(id)
    case id
    when Gosu::KB_1
      if @correct_answer == 0
        @question = "Parabéns, você acertou!"
      else
        @question = "Você errou. Tente novamente."
      end
    when Gosu::KB_2
      if @correct_answer == 1
        @question = "Parabéns, você acertou!"
      else
        @question = "Você errou. Tente novamente."
      end
    when Gosu::KB_3
      if @correct_answer == 2
        @question = "Parabéns, você acertou!"
      else
        @question = "Você errou. Tente novamente."
      end
    when Gosu::KB_4
      if @correct_answer == 3
        @question = "Parabéns, você acertou!"
      else
        @question = "Você errou. Tente novamente."
      end
    when Gosu::KB_E
      @edit_mode = !@edit_mode
    when Gosu::KB_UP
      if @edit_mode
        @edit_index -= 1
        @edit_index = 0 if @edit_index < 0
      end
    when Gosu::KB_DOWN
      if @edit_mode
        @edit_index += 1
        @edit_index = @options.length - 1 if @edit_index >= @options.length
      end
    when Gosu::KB_LEFT
      if @edit_mode
        @options[@edit_index] = @options[@edit_index][0..-2]
      end
    when Gosu::KB_RIGHT
      if @edit_mode
        @options[@edit_index] += " "
      end
    when Gosu::KB_ENTER
      if @edit_mode
        @edit_mode = false
        @correct_answer = @edit_index
      end
    end
  end
end

window = GameWindow.new
window.show
