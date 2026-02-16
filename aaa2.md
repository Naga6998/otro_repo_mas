```mermaid
classDiagram

    class Cliente {
        -id : int
        -nombre : String
        -email : String
        +realizarPedido() : void
        +getPedidos() : List<Pedido>
    }

    class Pedido {
        -id : int
        -fecha : Date
        -estado : String
        +addLinea() : void
        +getLineas() : List<LineaPedido>
    }

    class LineaPedido {
        -cantidad : int
        +getProducto() : Producto
    }

    class Producto {
        -id : int
        -nombre : String
        -precio : double
        +getPrecio() : double
    }

    Cliente "1" --> "0..*" Pedido
    Pedido "1" --> "1..*" LineaPedido
    LineaPedido "1" --> "1" Producto
