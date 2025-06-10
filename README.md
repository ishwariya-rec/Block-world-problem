# Block-world-problem
# blocks_world.py

class BlocksWorld:
    def __init__(self, blocks):
        self.world = [[block] for block in blocks]
    
 def find_block(self, block):
        for stack in self.world:
            if block in stack:
                return stack
        return None

   def move_onto(self, a, b):
        if a == b:
            print("Invalid move: same block")
            return
        source = self.find_block(a)
        target = self.find_block(b)
        if source is None or target is None:
            print("Invalid move: block not found")
            return
        if source == target:
            print("Invalid move: same stack")
            return
        while source[-1] != a:
            source.pop()
        while target[-1] != b:
            target.pop()
        block = source.pop()
        target.append(block)

  def move_over(self, a, b):
        if a == b:
            print("Invalid move: same block")
            return
        source = self.find_block(a)
        target = self.find_block(b)
        if source is None or target is None:
            print("Invalid move: block not found")
            return
        if source == target:
            print("Invalid move: same stack")
            return
        while source[-1] != a:
            source.pop()
        block = source.pop()
        target.append(block)

  def print_world(self):
        for i, stack in enumerate(self.world):
            print(f"{i}: {' '.join(stack)}")

# --------- Example Usage ---------

if __name__ == "__main__":
    blocks = ['A', 'B', 'C', 'D']
    bw = BlocksWorld(blocks)

  print("Initial World:")
    bw.print_world()

  print("\nMove A onto B:")
    bw.move_onto('A', 'B')
    bw.print_world()

  print("\nMove C over B:")
    bw.move_over('C', 'B')
    bw.print_world()

  print("\nMove D onto C:")
    bw.move_onto('D', 'C')
    bw.print_world()
