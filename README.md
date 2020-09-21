# 226.-Invert-Binary-Tree


`````c#
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left;
 *     public TreeNode right;
 *     public TreeNode(int val=0, TreeNode left=null, TreeNode right=null) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
public class Solution {
    public TreeNode InvertTree(TreeNode root) {
        if(root == null) return root;
        //BFS solution
        
        Queue<TreeNode> queue = new Queue<TreeNode>();
        queue.Enqueue(root);
        
        while(queue.Count > 0){
            var node = queue.Dequeue();
            //inversion
            TreeNode temp = node.left;
            node.left = node.right;
            node.right = temp;
            
            if(node.left != null){
                queue.Enqueue(node.left);
            }
            if(node.right != null){
                queue.Enqueue(node.right);
            } 
        }
        
                 
        return root;
    }
}
``````
