# flask-SQLAlchemy-many-to-many

db.create_all()
karim = User(name="Karim")
shah = User(name="Shahram")
amir = User(name="Amir")
action = Channel(name="Action")
drama = Channel(name="Drama")
romantic = Channel(name="Romantic")

db.session.add_all([karim, shah, amir, action, drama, romantic])
db.session.commit()

karim.following.append(drama)
db.session.commit()

karim.following
[Channel: Drama, Channel: Romantic]

drama.followers
[User: Karim, User: Shahram]

karim.following.remove(drama)
karim.following
[Channel: Romantic]
