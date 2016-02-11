
import java.awt.Graphics;
import java.awt.Color;
import java.awt.Graphics2D;
import java.awt.Rectangle;
import java.util.Random;

/**
 *
 * @author BlakeAllen
 */
public class Boss1 extends GameObject {

    Handler handler;
    static int damage = 0;
    Random rand = new Random();

    public Boss1(int x, int y, ID id, Handler handler, int Id) {
        super(x, y, id,Id);
        this.handler = handler;
        speedX = 0;
        speedY = 0;
        Id = Handler.counter;

    }

    public void tick() {
        x += speedX;
        y += speedY;            
        speedX = Game.clamp(speedX, -10, 10);
        int shoot = rand.nextInt(11);
        if (shoot % 3 == 0) {
            handler.add(new Bullet((int) x + 40, (int) y + 40, ID.Bullet, handler, handler.counter));
        }

        if (y <= 70 || y >= Game.HEIGHT - 62) {
            speedY *= -1;
        }
        if (x <= 0 || x >= Game.WIDTH - 76) {
            speedX *= -1;
        }

        x = Game.clamp((int) x, 0, Game.WIDTH - 26);
        y = Game.clamp((int) y, 70, Game.HEIGHT - 62);
    }

    public Rectangle getBounds() {
        return new Rectangle((int) x, (int) y, 80, 80);
    }

    public void render(Graphics g) {
        Graphics2D g2 = (Graphics2D) g;
        g.setColor(Color.YELLOW);
        g.fillRect((int) x, (int) y, 80, 80);
        g.setColor(Color.white);
        g.drawRect((int) x, (int) y, 80, 80);
    }
}
