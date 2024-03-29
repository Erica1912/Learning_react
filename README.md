# Learning_react


#### Conceptos de React

___TEMAS___

**¿Qué es React?**
- React es una biblioteca Javascript de código abierto diseñada para crear interfaces de usuario con el objetivo de facilitar el desarrollo de aplicaciones en una sola página.

**DOM Virtual**
  - El Virtual DOM es una representación del DOM guardada en memoria, que actúa de intermediario entre los estados de la aplicación y los estados del DOM (vistos por el usuario). Cuando ocurre un cambio en la aplicación web, el virtual DOM interpreta dichos cambios y calcula la manera más eficiente de actualizar el DOM para que renderice la menor cantidad de cambios posibles.
  
**Ciclo de vida**

- Es un proceso que React hace en cada componente, en algunos casos no podemos verlos como un bloque de código y en otros podemos llamarlos en nuestro componente para asignar una actividad según sea el caso necesario.

- Los componentes en react pasan por un Montaje, Actualización, Desmontaje y Manejo de errores.

    *Montaje:* En esta fase nuestro componente se crea junto a la lógica y los componentes internos y luego es insertado en el DOM.
     
    *Actualización:* En esta fase nuestro componente está al pendiente de cambios que pueden venir a través de un cambio en “state” o “props” 
                        esto en consecuencia realizan una acción dentro de un componente.
                        
    *Desmontaje:* En esta etapa nuestro componente “Muere” cuando nosotros no necesitamos un elemento de nuestra aplicación, podemos pasar por este ciclo de vida y de esta 
                    forma eliminar el componente de la representación que tiene en el DOM.

    *Manejo de Errores:* Cuando nuestro código se ejecuta y tiene un error, podemos entrar en una fase donde se puede entender mejor qué está sucediendo con la aplicación.

    Algo que debemos tener en cuenta es que un componente NO debe pasar por toda las fases, un componente puede ser montado y desmontado sin pasar por la fase 
    de actualización o manejo de errores.

    Ahora que entendemos las fases que cumple el ciclo de vida en React vamos a entrar a detalle en cada uno de ellos para ver qué piezas de código se ejecutan y 
    nos ayudarán a crear aplicaciones en React pasando por un ciclo de vida bien estructurado.

    *Montado:* 
     - Constructor() Este es el primer método al que se hace un llamado, aquí es donde se inicializan los métodos controladores, eventos del estado.
            
     - getDerivedStateFromProps() Este método se llama antes de presentarse en el DOM y nos permite actualizar el estado interno en respuesta a un cambio
              en las propiedades, es considerado un método de cuidado, ya que su implementación puede causar errores sutiles.
              
     - render() Si queremos representar elementos en el DOM en este método es donde se escribe esta lógica, usualmente utilizamos JSX para trabajar y presentar 
                nuestra aplicación.
                
     - ComponentDidMount() Este método se llama inmediatamente que ha sido montado en el DOM, aquí es donde trabajamos con eventos que permitan interactuar con 
                           nuestro componente.

    *Actualización:*        
     - getDerivedStateFromProps() Este método es el primero en ejecutarse en la fase de actualización y funciona de la misma forma que en el montaje.
        
     - shouldComponentUpdate() Dentro de este método se puede controlar la fase de actualización, podemos devolver un valor entre verdadero o 
            falso si queremos actualizar o no el componente y es utilizado principalmente para optimización.
        
     - render() Se llama el método render que representa los cambios en el DOM.
        
     - componentDidUpdate() Este método es invocado inmediatamente después de que el componente se actualiza y recibe como argumentos las propiedades y 
           el estado y es donde podemos manejar nuestro componente.

    *Desmontado:*
      - componentWillUnmount()Este método se llama justo antes de que el componente sea destruido o eliminado del DOM.
      
    *Manejo de Errores:*
     - getDerivedStateFromError() Una vez que se lanza un error este es el primer método que se llama, el cual recibe el error como argumento y cualquier 
         valor devuelto en este método es utilizado para actualizar el estado del componente.
         
     - componentDidCatch() Este método es llamado después de lanzarse un error y pasa como argumento el error y la información representada sobre el error.

    Ahora que entendemos cada una de las fases que tiene el ciclo de vida de react, podemos utilizarlas según sea necesario en nuestra aplicación y de esta forma crear 
    las interacciones que necesitemos.


**Props**
- Son la forma de enviar y recibir información en nuestros componentes. Son la forma de comunicar cada componente con el resto de la aplicación. 
  Son muy parecidas a los   parámetros y argumentos de las funciones en cualquier lenguaje de programación.

**State - Events**
- React permite responder a las interacciones de los usuarios con propiedades como: onClick, onChange, onKeyPress, onFocus, onScroll, entre otras.
   Estas propiedades reciben el nombre de la función que ejecuta el código que responde a las interacciones de los usuarios. Seguramente, esta función 
   usará la función *this.setState* para actualizar el estado de nuestro componente.
