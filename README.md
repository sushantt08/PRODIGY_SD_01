def celsius_to_fahrenheit(celsius):
    return (celsius * 9/5) + 32

def celsius_to_kelvin(celsius):
    return celsius + 273.15

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

def fahrenheit_to_kelvin(fahrenheit):
    return (fahrenheit - 32) * 5/9 + 273.15

def kelvin_to_celsius(kelvin):
    return kelvin - 273.15

def kelvin_to_fahrenheit(kelvin):
    return (kelvin - 273.15) * 9/5 + 32

def convert_temperature(value, unit):
    if unit == 'C':
        fahrenheit = celsius_to_fahrenheit(value)
        kelvin = celsius_to_kelvin(value)
        return (fahrenheit, kelvin)
    elif unit == 'F':
        celsius = fahrenheit_to_celsius(value)
        kelvin = fahrenheit_to_kelvin(value)
        return (celsius, kelvin)
    elif unit == 'K':
        celsius = kelvin_to_celsius(value)
        fahrenheit = kelvin_to_fahrenheit(value)
        return (celsius, fahrenheit)
    else:
        raise ValueError("Invalid unit of measurement. Use 'C' for Celsius, 'F' for Fahrenheit, or 'K' for Kelvin.")

def main():
    value = float(input("Enter the temperature value: "))
    unit = input("Enter the unit of measurement (C for Celsius, F for Fahrenheit, K for Kelvin): ").upper()
    
    try:
        converted_values = convert_temperature(value, unit)
        if unit == 'C':
            print(f"{value} degrees Celsius is {converted_values[0]:.2f} degrees Fahrenheit and {converted_values[1]:.2f} Kelvin.")
        elif unit == 'F':
            print(f"{value} degrees Fahrenheit is {converted_values[0]:.2f} degrees Celsius and {converted_values[1]:.2f} Kelvin.")
        elif unit == 'K':
            print(f"{value} Kelvin is {converted_values[0]:.2f} degrees Celsius and {converted_values[1]:.2f} degrees Fahrenheit.")
    except ValueError as e:
        print(e)

if __name__ == "__main__":
    main()
