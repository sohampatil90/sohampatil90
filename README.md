const readline = require("readline");

// Create interface for user input
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

// Function to take user input
function getUserInputs() {
    let farmData = {};

    rl.question("Enter land available (in acres): ", (land) => {
        farmData.land = parseFloat(land);

        rl.question("Enter soil type (e.g., sandy, loamy, clay): ", (soilType) => {
            farmData.soilType = soilType.toLowerCase();

            rl.question("Enter water availability (in liters per acre): ", (water) => {
                farmData.water = parseFloat(water);

                rl.question("Enter expected budget (in USD): ", (budget) => {
                    farmData.budget = parseFloat(budget);

                    rl.question("Enter current weather condition (e.g., rainy, dry, humid): ", (weather) => {
                        farmData.weather = weather.toLowerCase();

                        console.log("\nCollected Farm Data:");
                        console.log(farmData);

                        rl.close();
                    });
                });
            });
        });
    });
}

// Run the function to get input
getUserInputs();
