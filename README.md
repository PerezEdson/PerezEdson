Para ir a la : "go.mongodb.org/mongo-driver/mongo"

Ir a la : dep ensure -add "go.mongodb.org/mongo-driver/mongo"

Ir a la : import (
"contexto"
"tiempo"

Ir a la :
"go.mongodb.org/mongo-driver/mongo"
"go.mongodb.org/mongo-driver/mongo/opciones"
"go.mongodb.org/mongo-driver/mongo/readpref"
)

O abra el :
ctx, cancelar := context.WithTimeout(contexto.Background(), 10*tiempo.Segundo)
defer cancelar()
client, err := mongo.Connect(ctx, options.Client().ApplyURI("mongodb://localhost:27017"))

Os abra :
defer func() {
if err = client.Disconnect(ctx); err != nulo {
pánico(err)
}
}()

abra Os :
ctx, cancel = context.WithTimeout(context.Background(), 2*time.Second)
defer cancel()
err = client.Ping(ctx, readpref.Primary())

abra Os : 
collection := client.Database("testing").Collection("numbers")

abra Os iré 
ctx, cancel = context.WithTimeout(context.Background(), 5*time.Second)
defer cancel()
res, err := collection.InsertOne(ctx, bson.D{{"name", "pi"}, {"value", 3.14159}})
id := res.InsertedID

abra Os Iré :
import (
    "context"
    "log"
    "time"

Abra Os Marcho:
    "go.mongodb.org/mongo-driver/bson"
    "go.mongodb.org/mongo-driver/mongo"
    "go.mongodb.org/mongo-driver/mongo/options"
    "go.mongodb.org/mongo-driver/mongo/readpref"
)