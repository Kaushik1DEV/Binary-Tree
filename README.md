# Binary-Tree
Implementation Of Binary Tree



using System;
using System.Collections.Generic;
using System.Text;

namespace DataStructure
{
    public class TreeNode
    {
        public int data;
        public TreeNode left;
        public TreeNode right;

        public TreeNode(int data)
        {
            this.data = data;
        }
    }

    public class BinaryTree
    {
        public BinaryTree()
        {
            Console.WriteLine("****For null child pls enter -1");
        }

        public TreeNode BuildTree(TreeNode root)
        {

            Console.WriteLine("Pls enter the node value");
            int data = Convert.ToInt32(Console.ReadLine());

            if (data == -1)
            {
                return null;
            }

            root = new TreeNode(data);

            Console.WriteLine("pls enter the left value");
            root.left = BuildTree(root.left);
            Console.WriteLine("pls enter the right value");
            root.right = BuildTree(root.right);

            return root;
        }

        public void PirntTree(TreeNode root)
        {
            if (root == null) Console.WriteLine("Tree is empty");

            Queue<TreeNode> queue = new Queue<TreeNode>();
            queue.Enqueue(root);

            while (queue.Count > 0)
            {
                int size = queue.Count;

                while(size-- > 0)
                {
                    TreeNode temp = queue.Dequeue();
                    Console.Write(temp.data);

                    if(temp.left != null)
                    {
                        queue.Enqueue(temp.left);
                    }
                    if(temp.right != null)
                    {
                        queue.Enqueue(temp.right);
                    }

                }

                Console.WriteLine();    
            }
        }

    }
}
