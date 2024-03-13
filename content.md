# Find the Height of a Binary Tree 🌳

## The Problem
Write a Ruby function that:

- Takes the root node of a binary tree as input.
- Calculates the height of the tree, defined as the number of nodes along the longest path from the root node down to the farthest leaf node.
- Returns the height of the tree.

## Understand the Problem
Before diving into the binary tree height calculation, let's familiarize ourselves with the binary tree structure and the concept of tree height.

A binary tree is a data structure where each node has at most two children, referred to as the left child and the right child.
The height of a binary tree is measured as the number of nodes along the longest path from the root node to a leaf node.
For a simple binary tree:

![Example of a binary tree](./assets/binary-tree-ds.png)

A tree with only one node (the root) has a height of 1.
A tree with a root and one child has a height of 2.

## Think Aloud
When approaching this problem, consider using recursion to simplify your solution. Remember, interviewers want to see how you approach problems. Verbalize your thought process and write pseudocode as you break down the problem and explore solutions. It’s okay to start with a simpler, less efficient solution. You can always refine it later.

## Test your code

```ruby
class TreeNode
  attr_accessor :value, :left, :right

  def initialize(value = 0, left = nil, right = nil)
    @value = value
    @left = left
    @right = right
  end
end

def tree_height(node)
  # Your implementation here
end

# Example to test your method
root = TreeNode.new(1)
root.left = TreeNode.new(2)
root.right = TreeNode.new(3)
root.left.left = TreeNode.new(4)
root.left.right = TreeNode.new(5)
puts tree_height(root)
```
{: .repl #tree_height title="Find the Height of a Binary Tree" readonly_lines="[1,2,3,4,5,6,7,8,9]"}

```ruby
describe "Tree Height" do
  it "finds the height of a single-node tree" do
    root = TreeNode.new
    expect(tree_height(root)).to eq 1
  end
end
```
{: .repl-test #tree_height_test_1 for="tree_height" title="Tree Height for single-node tree" points="1"}

```ruby
describe "Tree Height" do
  it "finds the height of a 3-level binary tree" do
    root = TreeNode.new(1, TreeNode.new(2), TreeNode.new(3, nil, TreeNode.new(4)))
    expect(tree_height(root)).to eq 3
  end
end
```
{: .repl-test #tree_height_test_2 for="tree_height" title="Tree Height for a 3-level binary tree" points="1"}

```ruby
describe "Tree Height" do
  it "correctly identifies the height of an uneven tree" do
    root = TreeNode.new(1, TreeNode.new(2, TreeNode.new(3)), TreeNode.new(4))
    expect(tree_height(root)).to eq 3
  end
end
```
{: .repl-test #tree_height_test_3 for="tree_height" title="Tree Height for an uneven tree" points="1"}

## Tips and Clues for Solving the Problem
- **Recursion**: Recursion is a natural fit for many tree-related problems. Think about how you can break down the problem of finding the tree height into smaller, similar problems. Consider each node in the tree and think about how the height of the tree depends on the height of its subtrees.
- **Base Case**: The base case for recursion is usually a leaf node or a null node. Determine what the base case should be for this problem.
- **Combining Results**: When you call the function recursively for the left and right children of a node, you will need to combine these results to calculate the height at the current node.
- **Calculating Height**: To determine the height of the tree, you need to find the height of both the left and right subtrees of every node. Since each level of the tree adds one to the height, remember to add one for the current node itself.

## Quiz
- In a binary tree, each node can have how many children?
- One
  - Incorrect. While a node in a binary tree can have one child, this is not the limit.
- Two
  - Correct! A binary tree node can have at most two children: a left child and a right child.
- Multiple
  - Incorrect. In binary trees, each node is limited to two children. For multiple children without limit, consider general trees or other data structures.
{: .choose_best #node_children title="In a binary tree, each node can have how many children?" points="1" answer="2" }

- Which programming concept is often used to traverse a binary tree?
- Loops
  - Incorrect. While loops can be used, they are not the most common or straightforward method for tree traversal.
- Recursion
  - Correct! Recursion is a natural and common approach to traversing binary trees, as it simplifies the process of exploring each branch.
- Arrays
  - Incorrect. Arrays might be involved in tree implementation or to hold traversal results, but they are not the primary method for tree traversal.
{: .choose_best #traversal_method title="Which programming concept is often used to traverse a binary tree?" points="1" answer="2" }

- What does the height of a binary tree represent?
- The number of leaf nodes
  - Incorrect. The height is not measured by the number of leaf nodes.
- The depth of the deepest node
  - Correct! The height represents the number of nodes along the longest path from the root node down to the farthest leaf node.
- The total number of nodes
  - Incorrect. The height is concerned with the depth of the deepest node, not the total node count.
{: .choose_best #tree_height_meaning title="What does the height of a binary tree represent?" points="1" answer="2" }

## Conclusion
In this lesson, we've tackled the challenge of calculating the height of a binary tree. Through understanding binary tree structures, applying recursion, and solving test cases, you've developed a critical skill in tree traversal and manipulation. Keep practicing with different tree configurations to strengthen your understanding and efficiency in solving tree-related problems.