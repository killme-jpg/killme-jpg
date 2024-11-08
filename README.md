package tilee;

import java.awt.Graphics2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;
import main.GamePanel;

public class TileManager {

    GamePanel gp;
    Tile[] tile;

    private BufferedImage tile1;

        public TileManager(GamePanel gp) {

        // Initialize the tile array
        this.gp = gp;

        tile = new Tile[10];  // Assuming you plan to add more tiles later

        getTileImage();        // Load images for the tiles
    }

    public void getTileImage() {

        try {
            
            tile[0] = new Tile();
            tile[0].image = ImageIO.read(new File("/res/tiles/tile1.png"));

            tile[1] = new Tile();
            tile[1].image = ImageIO.read(new File("/res/tiles/tile2.png"));

            tile[3] = new Tile();
            tile[3].image = ImageIO.read(new File("/res/tiles/tile3.png"));
            
            // Alternatively, if you want to load from the file system (absolute path), make sure the file path is correct:
            // tile[0].image = ImageIO.read(new File("res/tiles/tile1.png"));

        } catch (IOException e) {
            e.printStackTrace();  // Handle the error more gracefully in production code (e.g., logging or showing an error message)
        }
    }

    public void draw(Graphics2D g2) {
        // Check if tile[0] and its image are loaded correctly
        if (image != null) {
            // Example positions to draw tiles
               
    g2.drawImage(tile[0].image, 0, 0, gp.tileSize, gp.tileSize, null);
    g2.drawImage(tile[0].image, 48, 0, gp.tileSize, gp.tileSize, null);
    g2.drawImage(tile[0].image, 96, 0, gp.tileSize, gp.tileSize, null);
    g2.drawImage(tile[0].image, 192, 0, gp.tileSize, gp.tileSize, null);
            }
        } else {
            // Handle case where the tile image isn't loaded
            System.out.println("Tile image is not loaded!");
        }
    }



