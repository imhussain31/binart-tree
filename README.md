```
        1
       / \
      2   3
     / \   \
    4   5   6
```
## Traversal Methods:
### Pre-order Traversal (Root -> Left -> Right):
```
Output: 1 2 4 5 3 6
```
### In-order Traversal (Left -> Root -> Right):
```
Output: 4 2 5 1 3 6
```
### Post-order Traversal (Left -> Right -> Root):
```
Output: 4 5 2 6 3 1
```
### Level-order Traversal (Breadth-First Traversal):
```
Output: 1 2 3 4 5 6
```

## Java Code for Tree Traversal
```JAVA
class TreeNode {
    int val;
    TreeNode left, right;

    TreeNode(int val) {
        this.val = val;
        this.left = null;
        this.right = null;
    }
}

public class BinaryTreeTraversal {

    // Pre-order Traversal
    public void preOrder(TreeNode root) {
        if (root == null) return;
        System.out.print(root.val + " ");
        preOrder(root.left);
        preOrder(root.right);
    }

    // In-order Traversal
    public void inOrder(TreeNode root) {
        if (root == null) return;
        inOrder(root.left);
        System.out.print(root.val + " ");
        inOrder(root.right);
    }

    // Post-order Traversal
    public void postOrder(TreeNode root) {
        if (root == null) return;
        postOrder(root.left);
        postOrder(root.right);
        System.out.print(root.val + " ");
    }

    // Level-order Traversal (using a Queue)
    public void levelOrder(TreeNode root) {
        if (root == null) return;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root);

        while (!queue.isEmpty()) {
            TreeNode current = queue.poll();
            System.out.print(current.val + " ");

            if (current.left != null) queue.add(current.left);
            if (current.right != null) queue.add(current.right);
        }
    }

    public static void main(String[] args) {
        // Building the example tree:
        //         1
        //        / \
        //       2   3
        //      / \   \
        //     4   5   6
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);
        root.right.right = new TreeNode(6);

        BinaryTreeTraversal traversal = new BinaryTreeTraversal();

        System.out.println("Pre-order Traversal:");
        traversal.preOrder(root);
        System.out.println();

        System.out.println("In-order Traversal:");
        traversal.inOrder(root);
        System.out.println();

        System.out.println("Post-order Traversal:");
        traversal.postOrder(root);
        System.out.println();

        System.out.println("Level-order Traversal:");
        traversal.levelOrder(root);
        System.out.println();
    }
}

```

