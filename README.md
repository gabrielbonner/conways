# conways

class Cell
  attr_accessor :living
  attr_reader :position_x, :position_y

  def initialize(position_x, position_y, living = false)
    @living = living
    @position_x = position_x
    @position_y = position_y
  end

  def living?
    @living
  end

end


class Map
  attr_accessor :height, :width, :cells

  def initialize(size)
    @height = size
    @width = size
    @cells = []

    width.times do |w|
      height.times do |h|
        cells << Cell.new(w, h)
      end
    end
  end

  def pretty
    height.times do |h|
      width.times do |w|
        if cells[w+h].living?
          print "|O| "
        else
          print "|X| "
        end
      end
      puts
      puts
    end
  end

  def tick



  end

  def number_of_neighbors(cell)

    neighbors_count = 0

    x = cell.position_x
    y = cell.position_y

    # cells.find
    cells.each do |cell|
      if cell.position_x == x - 1 && cell.position_y == y - 1
        return cell
      end
      # cell.position_x == x-1 && cell.position_y == y

    # if cell.position_x > 0 || cell.position_x < width
    end

    # 1, 1
    #
    # x-1, y-1
    # x-1, y
    # x-1, y+1
    #
    # x, y-1
    # x, y
    # x, y+1
    #
    # x+1, y-1
    # x+1, y
    # x+1, y+1
    #
    #

  end

end

map = Map.new(9)
map.pretty

# class Game
#   def initialize(height, width)
#     @map = Map.new(height, width)
#   end
#
#   def tick
#     # map checks cells
#   end
# end
