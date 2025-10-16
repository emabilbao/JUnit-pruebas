# JUnit-pruebas
Pruebas con JUnit
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class ConversorTemperaturaTest {

    @Test
    void testConversionCelsiusAFahrenheit() {
        ConversorTemperatura conversor = new ConversorTemperatura();
        double resultado = conversor.celsiusAFahrenheit(0);
        assertEquals(32.0, resultado, 0.001); // margen de error de 0.001
    }

    @Test
    void testConversionCienCelsiusAFahrenheit() {
        ConversorTemperatura conversor = new ConversorTemperatura();
        double resultado = conversor.celsiusAFahrenheit(100);
        assertEquals(212.0, resultado, 0.001);
    }
}

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class CuentaBancariaTest {

    @Test
    void testDepositar() {
        CuentaBancaria cuenta = new CuentaBancaria(100);
        cuenta.depositar(50);
        assertEquals(150, cuenta.getSaldo());
    }

    @Test
    void testRetiroValido() {
        CuentaBancaria cuenta = new CuentaBancaria(200);
        cuenta.retirar(100);
        assertEquals(100, cuenta.getSaldo());
    }

    @Test
    void testRetiroMayorQueSaldoDebeFallar() {
        CuentaBancaria cuenta = new CuentaBancaria(100);
        assertThrows(IllegalArgumentException.class, () -> cuenta.retirar(150));
    }
}

public class ConversorTemperatura {
    public double celsiusAFahrenheit(double celsius) {
        return (celsius * 9 / 5) + 32;
    }
}

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class ConversorTemperaturaTest {

    @Test
    void testConversionCelsiusAFahrenheit() {
        ConversorTemperatura conversor = new ConversorTemperatura();
        double resultado = conversor.celsiusAFahrenheit(0);
        assertEquals(32.0, resultado, 0.001); // margen de error de 0.001
    }

    @Test
    void testConversionCienCelsiusAFahrenheit() {
        ConversorTemperatura conversor = new ConversorTemperatura();
        double resultado = conversor.celsiusAFahrenheit(100);
        assertEquals(212.0, resultado, 0.001);
    }
}

public class Validador {
    public void procesar(String valor) {
        if (valor == null) {
            throw new NullPointerException("El valor no puede ser nulo");
        }
        // algún procesamiento ficticio
    }
}

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class ValidadorTest {

    @Test
    void testProcesarValorNuloLanzaExcepcion() {
        Validador validador = new Validador();
        assertThrows(NullPointerException.class, () -> validador.procesar(null));
    }
}
