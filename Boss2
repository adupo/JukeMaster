
import java.awt.Graphics;
import java.awt.Color;
import java.awt.Graphics2D;
import java.awt.Rectangle;
import java.util.Random;

/**
 *
 * @author BlakeAllen
 */
public class Boss2 extends GameObject {

    Handler handler;
    static int damage = 25;
    Random rand = new Random();
    private int timer = 150;
    private int timer2 = 50;

    public Boss2(int x, int y, ID id, Handler handler, int Id) {
        super(x, y, id, Id);
        this.handler = handler;
        speedX = 0;
        speedY = 0;
        Id = Handler.counter;

    }

    public void tick() {
        x += speedX;
        y += speedY;
        if (timer <= 0) {
            speedY = 0;
        } else {
            timer--;
        }

        if (timer <= 0) {
            timer2--;
        }
        if (timer2 <= 0) {
            if (speedX == 0) {
                speedX = 2;
            }
            if (speedX < 0) {
                speedX -= .01f;
            } else {
                speedX += .01f;
            }

            speedX = Game.clamp(speedX, -10, 10);
            int shoot = rand.nextInt(11);
            if (shoot % 2 == 0) {
                handler.add(new Bullet((int) x + 40, (int) y + 40,"Bullet2", ID.Bullet, handler, handler.counter));
            }

            if (y <= 70 || y >= Game.HEIGHT - 62) {
                speedY *= -1;
            }
            if (x <= 0 || x >= Game.WIDTH - 67) {
                speedX *= -1;
            }

            x = Game.clamp((int) x, 0, Game.WIDTH - 67);
            y = Game.clamp((int) y, 70, Game.HEIGHT - 62);
        }
    }

    @Override
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
