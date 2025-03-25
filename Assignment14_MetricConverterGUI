import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import javafx.stage.Stage;

public class MetricConverterGUI extends Application {

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Metric Converter");

        // Input field
        TextField inputField = new TextField();
        inputField.setPromptText("Enter value");

        // ComboBox for selecting conversion type
        ComboBox<String> conversionType = new ComboBox<>();
        conversionType.getItems().addAll("km to m", "cm to mm", "ft to in", "kg to g");
        conversionType.setPromptText("Select Conversion");

        // Button to perform conversion
        Button convertButton = new Button("Convert");

        // Label to display result
        Label resultLabel = new Label();

        // Exit button
        Button exitButton = new Button("Exit");
        exitButton.setOnAction(e -> primaryStage.close());

        // Action on button click
        convertButton.setOnAction(e -> {
            try {
                double inputValue = Double.parseDouble(inputField.getText());
                String type = conversionType.getValue();

                if (type == null) {
                    resultLabel.setText("Please select a conversion type.");
                    return;
                }

                double result = 0;
                String output = "";

                switch (type) {
                    case "km to m":
                        result = inputValue * 1000;
                        output = inputValue + " km = " + result + " m";
                        break;
                    case "cm to mm":
                        result = inputValue * 10;
                        output = inputValue + " cm = " + result + " mm";
                        break;
                    case "ft to in":
                        result = inputValue * 12;
                        output = inputValue + " ft = " + result + " in";
                        break;
                    case "kg to g":
                        result = inputValue * 1000;
                        output = inputValue + " kg = " + result + " g";
                        break;
                    default:
                        output = "Unknown conversion.";
                }

                resultLabel.setText(output);
            } catch (NumberFormatException ex) {
                resultLabel.setText("Invalid input. Please enter a number.");
            }
        });

        VBox layout = new VBox(10);
        layout.getChildren().addAll(
                new Label("Metric Converter"),
                inputField,
                conversionType,
                convertButton,
                resultLabel,
                exitButton
        );

        layout.setStyle("-fx-padding: 20; -fx-alignment: center;");

        Scene scene = new Scene(layout, 350, 300);
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}

