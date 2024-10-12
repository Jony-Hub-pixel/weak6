using System;

public abstract class Transport
{
    // Абстрактный метод для расчета времени поездки
    public abstract double CalculateTravelTime(double distance);
    
    // Абстрактный метод для получения информации о транспортном средстве
    public abstract string GetTransportInfo();
}

public class Car : Transport
{
    private const double AverageSpeed = 80.0; // Средняя скорость автомобиля в км/ч

    // Реализация расчета времени поездки для автомобиля
    public override double CalculateTravelTime(double distance)
    {
        return distance / AverageSpeed; // Время = Расстояние / Скорость
    }

    // Реализация получения информации о автомобиле
    public override string GetTransportInfo()
    {
        return "Transport Type: Car\nAverage Speed: 80 km/h";
    }
}

public class Plane : Transport
{
    private const double AverageSpeed = 600.0; // Средняя скорость самолета в км/ч

    // Реализация расчета времени поездки для самолета
    public override double CalculateTravelTime(double distance)
    {
        return distance / AverageSpeed; // Время = Расстояние / Скорость
    }

    // Реализация получения информации о самолете
    public override string GetTransportInfo()
    {
        return "Transport Type: Plane\nAverage Speed: 600 km/h";
    }
}

class Program
{
    static void Main(string[] args)
    {
        double distance = 480; // Заданное расстояние в км

        // Создаем объекты автомобиля и самолета
        Transport car = new Car();
        Transport plane = new Plane();

        // Вычисляем время поездки для автомобиля
        double carTravelTime = car.CalculateTravelTime(distance);
        Console.WriteLine(car.GetTransportInfo());
        Console.WriteLine($"Travel Time for Car: {carTravelTime} hours");

        // Вычисляем время поездки для самолета
        double planeTravelTime = plane.CalculateTravelTime(distance);
        Console.WriteLine(plane.GetTransportInfo());
        Console.WriteLine($"Travel Time for Plane: {planeTravelTime} hours");
    }
}
