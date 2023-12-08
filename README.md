# Software-engineering-project#
import java.util.ArrayList;
import java.util.List;

class Driver {
    private String name;
    private String gender;
    private double rating;
    private String vehicleType;

    public Driver(String name, String gender, double rating, String vehicleType) {
        this.name = name;
        this.gender = gender;
        this.rating = rating;
        this.vehicleType = vehicleType;
    }

    public String getName() {
        return name;
    }

    public String getGender() {
        return gender;
    }

    public double getRating() {
        return rating;
    }

    public String getVehicleType() {
        return vehicleType;
    }
}

class Rider {
    private String name;
    private String preferredGender;
    private double preferredRating;
    private String preferredVehicleType;

    public Rider(String name, String preferredGender, double preferredRating, String preferredVehicleType) {
        this.name = name;
        this.preferredGender = preferredGender;
        this.preferredRating = preferredRating;
        this.preferredVehicleType = preferredVehicleType;
    }

    public String getName() {
        return name;
    }

    public String getPreferredGender() {
        return preferredGender;
    }

    public double getPreferredRating() {
        return preferredRating;
    }

    public String getPreferredVehicleType() {
        return preferredVehicleType;
    }
}

class RideService {
    private List<Driver> drivers;

    public RideService() {
        drivers = new ArrayList<>();
    }

    public void addDriver(Driver driver) {
        drivers.add(driver);
    }

    public Driver findPreferredDriver(Rider rider) {
        for (Driver driver : drivers) {
            if (driver.getGender().equals(rider.getPreferredGender()) &&
                driver.getRating() >= rider.getPreferredRating() &&
                driver.getVehicleType().equals(rider.getPreferredVehicleType())) {
                return driver;
            }
        }
        return null;
    }
}

public class Main {
    public static void main(String[] args) {
        RideService rideService = new RideService();

        // Add some drivers
        rideService.addDriver(new Driver("John", "Male", 4.8, "Sedan"));
        rideService.addDriver(new Driver("Lisa", "Female", 4.9, "SUV"));
        rideService.addDriver(new Driver("David", "Male", 4.7, "Hatchback
