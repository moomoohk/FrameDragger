FrameDragger
============

This super easy to use tool will make your JFrames (and other Swing/AWT Components) draggable on the screen!

Why would I ever use this?
--------------------------

Good question!

Suppose you had an undecorated JFrame, which of course has no title bar, and you wanted to grant users the ability to drag around said undecorated JFrame.

In this case all you'd have to do is import this library (it's just one class) and add one line of code (see examples), and voila!

Examples
--------

    public class FrameDraggerTest
    {
        public static void main(String[] args)
        {
            JFrame frame = new JFrame("Drag me!");
            frame.setSize(200, 200);
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setLocationRelativeTo(null);
            new FrameDragger().applyTo(frame); // <----- This is all you need to add.
            frame.setVisible(true);
        }
    }

You can even add event hooks for mouse press, mouse release and mouse drag events like so:

    public class FrameDraggerTest
    {
        public static void main(String[] args)
        {
            JFrame frame = new JFrame("Drag me!");
            frame.setSize(200, 200);
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setLocationRelativeTo(null);
            Runnable onPress = new Runnable()
            {
                public void run()
                {
                    System.out.println("Press!");
                }
            };
            Runnable onRelease = new Runnable()
            {
                public void run()
                {
                    System.out.println("Release!");
                }
            };
            Runnable onDrag = new Runnable()
            {
                public void run()
                {
                    System.out.println("Drag!");
                }
            };
            new FrameDragger().applyTo(frame);
            frame.setVisible(true);
        }
    }
