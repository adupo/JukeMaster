
import java.awt.Graphics;
import java.awt.Color;
import java.awt.Graphics2D;
import java.awt.Rectangle;
import java.util.Random;

/**
 *
 * @author BlakeAllen
 */
public class Bullet extends GameObject {
    Handler handler;
    static int damage = 1;
    Random rand = new Random();

    public Bullet(int x, int y, ID id, Handler handler, int Id) {
        super(x, y, id, Id);
        this.handler = handler;
        speedX = rand.nextInt(10 - -10) + -10;
        speedY = rand.nextInt(10 - -10) + -10;
		Id = Handler.counter;
    }

    public Bullet(int x, int y, String name, ID id, Handler handler, int Id) {
        super(x, y, id, Id);
        this.handler = handler;
        speedX = 0;
        speedY = (rand.nextInt(5) + 2) - 1;

    }

    public void tick() {
        x += speedX;
        y += speedY;
        if (y >= Game.HEIGHT || y <= 0) {
            handler.remove(Id);
        } else if (x >= Game.WIDTH || x <= 0) {
            handler.remove(Id);
        }
        if (Player.collisionB) {
            handler.remove(Player.removeId);
            Player.collisionB = false;
    	}
    	
    }

    public Rectangle getBounds() {
        return new Rectangle((int) x, (int) y, 8, 8);
    }

    public void render(Graphics g) {
        Graphics2D g2 = (Graphics2D) g;
        g.setColor(Color.RED);
        g.fillRect((int) x, (int) y, 8, 8);
        g.setColor(Color.white);
        g.drawRect((int) x, (int) y, 8, 8);
    }
}
