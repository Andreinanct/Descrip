## CLASES
## public class BancoLogix {
La clase BancoLogix es responsable de la administración principal del sistema bancario.

 * Administra el flujo de transacciones, gestión de usuarios y cuentas, e interacción con la interfaz gráfica.
 * Esta clase sirve como el punto central de lógica de negocio y vinculación entre la capa de datos y la interfaz.
 * Responsabilidades clave incluyen:
   
   - Gestión de cuentas de usuario
   - Procesamiento de transacciones como depósitos, retiros y transferencias
   - Generación de informes y registros de transacciones
   - Interacción con la interfaz gráfica para mostrar ventanas de consulta, depósitos, retiros, etc.
     
 ## public class Usuario {
  La clase Usuario representa a un cliente del banco, con sus datos personales y de cuenta.
    
    Un objeto Usuario contiene información como el nombre, el número de cuenta, y el saldo disponible.
    También tiene métodos para realizar operaciones sobre la cuenta del usuario.

## 
## ATRIBUTOS
 ## private List<Usuario> usuarios;
  Almacena la lista de todos los usuarios registrados en el banco.
    
    Esta lista es utilizada para buscar usuarios por número de cuenta o ID, así como para
    realizar operaciones en las cuentas de los usuarios.

 ## private double saldo;
   El saldo disponible en la cuenta del usuario.
     Este valor se actualiza cada vez que se realiza una operación de depósito o retiro.

     
 ##
 ## CONSTRUCTORES    

 ## public BancoLogix(String datosUsuarios) throws IOException {
   Constructor de la clase BancoLogix. Inicializa el sistema bancario cargando los datos
   de los usuarios y preparando la interfaz gráfica.
    
     @param datosUsuarios Archivo o base de datos de usuarios a cargar en el sistema.
     @throws IOException Si ocurre un error al cargar los datos de los usuarios.

 ## public void depositar(String numeroCuenta, double monto) throws CuentaNoEncontradaException, MontoInvalidoException {
   Realiza un depósito en la cuenta del usuario.

     @param numeroCuenta El número de cuenta del usuario en el que se realizará el depósito.
     @param monto La cantidad de dinero a depositar. Debe ser un valor positivo.
     @throws CuentaNoEncontradaException Si el número de cuenta no está registrado en el sistema.
     @throws MontoInvalidoException Si el monto es cero o negativo.

 ## public void retirar(String numeroCuenta, double monto) throws CuentaNoEncontradaException, SaldoInsuficienteException {
   Realiza un retiro de la cuenta del usuario.

     @param numeroCuenta El número de cuenta del usuario que desea hacer el retiro.
     @param monto El monto a retirar. Debe ser un valor positivo y no exceder el saldo actual.
     @throws CuentaNoEncontradaException Si el número de cuenta no está registrado en el sistema.
     @throws SaldoInsuficienteException Si el saldo es insuficiente para cubrir el monto del retiro.

 ## public void transferir(String cuentaOrigen, String cuentaDestino, double monto) throws CuentaNoEncontradaException, SaldoInsuficienteException {
   Realiza una transferencia de fondos entre dos cuentas.

     @param cuentaOrigen El número de cuenta desde donde se retiran los fondos.
     @param cuentaDestino El número de cuenta que recibirá los fondos.
     @param monto La cantidad de dinero a transferir. Debe ser un valor positivo y no exceder el saldo disponible en la cuenta origen.
     @throws CuentaNoEncontradaException Si alguna de las cuentas no está registrada en el sistema.
     @throws SaldoInsuficienteException Si la cuenta origen no tiene fondos suficientes para la transferencia.

     
##
## MANEJO DE EVENTOS

## public void actionPerformed(ActionEvent e) {
  Maneja los eventos de acción relacionados con las transacciones en la interfaz gráfica.
  Responde a eventos de botones como "Consultar Saldo", "Depositar", "Retirar" y "Transferir".
 
    @param e El evento de acción que desencadenó la operación.

    
##
## INTERACCIÓN CON OTRAS CLASES

## public Usuario buscarUsuario(String numeroCuenta) {
  Busca un usuario en el sistema utilizando su número de cuenta.

    @param numeroCuenta El número de cuenta a buscar.
    @return El objeto Usuario correspondiente si se encuentra; null en caso contrario.
    @see Usuario
  
