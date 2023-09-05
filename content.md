# Ruby Gym: BlackJack

Write a program to play a variety of BlackJack. (In our version, the numbers can be between 1 and 13.)

The program ingests an array of `numbers`, and it should print their sum.

Here's the catch: 
 
- If the sum is greater than 21, return 0, unless one of the numbers is 11. 
- In such a case, the 11 should be 'converted' to a 1 to prevent the sum from being exceeded.

For example, given 11 and 13 as input, the 11 should be 'converted' into a 1 so the total sum printed will be 14.

Use the `numbers` array below to write your solution. Your code should always start by extracting from the `numbers` array.

Hint: It may be helpful to use the `.include?` method on the array; [see the Ruby reference](https://learn.firstdraft.com/lessons/33#include-array)

```ruby
numbers = [rand(1..13), rand(1..13)]
pp numbers
# write your program below
```
{: .repl #blackjack title="BlackJack" readonly_lines="[1,2,3]"}


```ruby
describe "BlackJack" do
  it "prints '20' when the numbers are '[10, 10]'" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Kernel).to receive(:rand).and_return(10, 10)
    expect { require_relative(path) }.to output(/20/).to_stdout
  end
end
```
{: .repl-test #blackjack_test_1 for="blackjack" title="BlackJack Test 1" points="1"}


```ruby
describe "BlackJack" do
  it "prints '14' when the numbers are '[13, 11]'" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Kernel).to receive(:rand).and_return(13, 11)
    expect { require_relative(path) }.to output(/14/).to_stdout
  end
end
```
{: .repl-test #blackjack_test_2 for="blackjack" title="BlackJack Test 2" points="1"}


```ruby
describe "BlackJack" do
  it "prints '0' when the numbers are '[13, 13]'" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Kernel).to receive(:rand).and_return(13, 13)
    expect { require_relative(path) }.to output(/0/).to_stdout
  end
end
```
{: .repl-test #blackjack_test_3 for="blackjack" title="BlackJack Test 3" points="1"}


```ruby
describe "BlackJack" do
  it "prints '12' when the numbers are '[11, 11]'" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Kernel).to receive(:rand).and_return(11, 11)
    expect { require_relative(path) }.to output(/12/).to_stdout
  end
end
```
{: .repl-test #blackjack_test_4 for="blackjack" title="BlackJack Test 4" points="1"}
