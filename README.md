# railsAPI
Creando una api en ruby rails

# Iniciamos una aplicacion especializada para api con
rails new app --api

# Podemos modificar los datos que devuelve nuestra api con la gema serializer

gem 'active_model_serializers'

generamos un serializer para el modelo que queremos modificar

rails g serializer user

En este serializer podemos modificar los datos a mostrar, e incluso crear datos personalizados
class UserSerializer < ActiveModel::Serializer
  attributes :id, :name, :email, :name_and_email
  def name_and_email
    "#{object.name}: #{object.email}"
  end
end
