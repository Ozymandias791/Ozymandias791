import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.shape.Rectangle;
import javafx.stage.Stage;

public class SimpleJavaFXAnimation extends Application {

    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Rectangle rectangle = new Rectangle(100, 100);
        rectangle.setFill(Color.RED);

        Group group = new Group(rectangle);
        Scene scene = new Scene(group, 300, 300);

        primaryStage.setScene(scene);
        primaryStage.show();

        rectangle.setTranslateX(0);
        rectangle.setTranslateY(0);

        TranslateTransition translateTransition = new TranslateTransition(Duration.seconds(2), rectangle);
        translateTransition.setByX(150);
        translateTransition.setByY(150);
        translateTransition.play();
    }
}
