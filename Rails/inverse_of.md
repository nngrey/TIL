#inverse_of

Add inverse_of to a belongs_to relationship, except if it through or as relationship:

class Client < ApplicationRecord
  has_one :client_configuration, inverse_of: :client
end

class ClientConfiguration < ApplicationRecord
  belongs_to :client, inverse_of: :client_configuration
end