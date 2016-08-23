#Foreign Keys

I always get confused about when to add a foreign key and an index to a reference. Based on my research, it seems like it is generally a good idea to do both.

Always add a foreign_key and an index to a reference:

```
def change
  create_table :client_configurations do |t|
    t.references :client, foreign_key: true, index: true
    t.timestamps
  end
end
```