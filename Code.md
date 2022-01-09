# Blockchain-with-crypto-transaction-feature
python script that asks users for their name, who they are sending J2 coin too(fictional cryptocurrency) and how much they're sending. it then prints the transaction detail in words and prints the hash number of the block

import hashlib
#here im asking for the info of the users transaction
class input_data:
      def __init__(self, sender, reciever, amount):
          self.sender = sender
          self.reciever = reciever
          self.amount = amount

sender = input("what is your name? ")
reciever = input("who would you like to send J2 coin to? ")
amount = input("how much J2 coin would you like to send?: ")

#creating the j2 coin block
class JoshSquaredBlock:

    #in a block it needs the previous block hash and the list of transaction for this block
    def __init__(self, previous_block_hash, input_data):
        self.previous_block_hash = previous_block_hash
        self.input_data = input_data

        #calculating the hash number of the block
        self.block_data = "-"+ str(input_data) + "-" +previous_block_hash
        self.block_hash = hashlib.sha256(self.block_data.encode()).hexdigest()


#defining the first block. "Initial string" is used as it s the first block in the chain
block = JoshSquaredBlock("", sender + " has sent " + amount + " J2 coin to " + reciever)


print(block.block_data)

print(block.block_hash)
