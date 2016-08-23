#accepts_nested_attributes_for

Add accepts_nested_attributes_for to the parent class if you want to save attributes on associated records through the parent:

```
class Client < ApplicationRecord
  has_one :client_configuration, inverse_of: :client

  accepts_nested_attributes_for :client_configuration
end

class ClientConfiguration < ApplicationRecord
  belongs_to :client, inverse_of: :client_configuration
end
```