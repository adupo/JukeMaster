
import java.awt.Graphics;
import java.awt.Color;
import java.awt.Graphics2D;
import java.awt.Rectangle;

/**
 *
 * @author BlakeAllen
 */
public class Enemy extends GameObject {

    Handler handler;
    static int damage = 4;

    public Enemy(int x, int y, ID id, Handler handler, int Id) {
        super(x, y, id, Id);
        this.handler = handler;
        speedX = 1;
        speedY = 1;
        Id = Handler.counter;

    }

    public void tick() {
        x += speedX;
        y += speedY;
        if (y <= 70 || y >= Game.HEIGHT - 47) {
            speedY *= -1;
        }
        if (x <= 0 || x >= Game.WIDTH - 26) {
            speedX *= -1;
        }

        x = Game.clamp((int) x, 0, Game.WIDTH - 26);
        y = Game.clamp((int) y, 70, Game.HEIGHT - 47);
    }

    public Rectangle getBounds() {
        return new Rectangle((int) x, (int) y, 24, 24);
    }

    public void render(Graphics g) {
        Graphics2D g2 = (Graphics2D) g;
        g.setColor(Color.BLACK);
        g.fillRect((int) x, (int) y, 24, 24);
        g.setColor(Color.white);
        g.drawRect((int) x, (int) y, 24, 24);
    }
}
