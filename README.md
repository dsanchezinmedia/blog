 * @author Ing. Rosendo Leonardo Hernández Claro <rosendo.hernandez@inmediastudio.com>
 
# VAUGHAN API
#### API to manage the business logic for Vaughan 

API methods usage:
route prefix: /api

### Installation
 1. Console:
```sh
git clone https://github.com/inmediastudio/vaughan_api.git
cd vaughan_api
composer update
```
 2. Copy .env file and modify the database:
 3. Console:
```sh
mkdir -pv bootstrap/cache storage/framework/views storage/app storage/framework/sessions storage/framework/cache
chmod -R 0777 bootstrap/ storage/

php -a
$path = 'database/migrations/';
$dir = opendir($path);
while ($file = readdir($dir))
if($file !== '.' && $file !== '..' && $file !== '.gitkeep')
{
  $part = explode("_", $file);
  $date = $part[0].$part[1].$part[2].$part[3];

  if($date >= 20161201090851)
  {
    echo "Fichero borrado: ". $file."\n";
    unlink($path.$file);
  }
}
exit

php artisan migrate
```

 4. Entramos a http://client.vaughan.com/ y nos logeamos con el usuario:
Usuario: inmedia_ldap
Contraseña: 2SIFkMBCmL

 5. Consola
```sh
git checkout database/
php artisan migrate
git checkout database/migrations/
php artisan migrate
```

### Configuration

#### Lego Status
##### List
**name:** index
**path:** /legoStatuses
**Http method:** GET
**Description:** Get a listing of the Lego Statuses.
**Optional parameters:** 
with*{semicolon relationships(legos;boxes;teachingPoints;phases;courses)}*
limit*{integer}*
offset*{integer}*
search
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /legoStatuses/{id}
**Http method:** GET
**Description:** Display the specified Lego Status
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /legoStatuses
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /legoStatuses/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /legoStatuses/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### Lego Type
##### List
**name:** index
**path:** /legoTypes
**Http method:** GET
**Description:** Get a listing of the Lego Types.
**Optional parameters:** 
with*{semicolon relationships(legos;boxes)}*
limit*{integer}*
offset*{integer}*
search
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /legoTypes/{id}
**Http method:** GET
**Description:** Display the specified Lego Type
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /legoTypes
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /legoTypes/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /legoTypes/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### Lego Priority 
##### List
**name:** index
**path:** /legoPriorities
**Http method:** GET
**Description:** Get a listing of the Lego Priorities.
**Optional parameters:** 
with
limit*{integer}*
offset*{integer}*
search
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /legoPriorities/{id}
**Http method:** GET
**Description:** Display the specified Lego Priority
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /legoPriorities
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /legoPriorities/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /legoPriorities/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### Stage 
##### List
**name:** index
**path:** /stages
**Http method:** GET
**Description:** Get a listing of the Stages.
**Optional parameters:** 
with*{semicolon relationships(boxes)}*
limit*{integer}*
offset*{integer}*
search
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /stages/{id}
**Http method:** GET
**Description:** Display the specified Stage
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /stages
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /stages/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /stages/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### File Type 
##### List
**name:** index
**path:** /fileTypes
**Http method:** GET
**Description:** Get a listing of the File Types.
**Optional parameters:** 
with*{semicolon relationships(files)}*
limit*{integer}*
offset*{integer}*
search
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /fileTypes/{id}
**Http method:** GET
**Description:** Display the specified File Type
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /fileTypes
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /fileTypes/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /fileTypes/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### File Request Status 
##### List
**name:** index
**path:** /fileRequestStatuses
**Http method:** GET
**Description:** Get a listing of the File Request Statuses.
**Optional parameters:** 
with*{semicolon relationships(fileRequests)}*
limit*{integer}*
offset*{integer}*
search
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /fileRequestStatuses/{id}
**Http method:** GET
**Description:** Display the specified File Request Status
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /fileRequestStatuses
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /fileRequestStatuses/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /fileRequestStatuses/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

### Modules

#### Course
##### List
**name:** index
**path:** /courses
**Http method:** GET
**Description:** Get a listing of the Courses.
**Optional parameters:** 
with*{semicolon relationships(status;createdBy;phases;teachingPoints)}*
limit*{integer}*
offset*{integer}*
search*{name:_name;favourite:_favourite(boolean);owner.email:_email;status.name:_statusName;status.id:_statusId}*
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /courses/{id}
**Http method:** GET
**Description:** Display the specified Course
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /courses
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /courses/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /courses/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### Phase 
##### List
**name:** index
**path:** /phases
**Http method:** GET
**Description:** Get a listing of the Phases.
**Optional parameters:** 
with*{semicolon relationships(status;createdBy;owner;courses;teachingPoints)}*
limit*{integer}*
offset*{integer}*
search*{courses.id:_courseId;owner.email:_email;status.name:_statusName;status.id:_statusId}*
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /phases/{id}
**Http method:** GET
**Description:** Display the specified Phase
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /phases
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /phases/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /phases/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### Teaching Point 
##### List
**name:** index
**path:** /teachingPoints
**Http method:** GET
**Description:** Get a listing of the Teaching Points.
**Optional parameters:** 
with*{semicolon relationships(status;createdBy;owner;courses;phases;boxes)}*
limit*{integer}*
offset*{integer}*
search*{name:_name;owner.email:_email;status.name:_statusName;status.id:_statusId}*
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /teachingPoints/{id}
**Http method:** GET
**Description:** Display the specified Teaching Point
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /teachingPoints
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /teachingPoints/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /teachingPoints/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### Box
##### List
**name:** index
**path:** /boxes
**Http method:** GET
**Description:** Get a listing of the Boxes.
**Optional parameters:** 
with*{semicolon relationships(stage;status;type;createdBy;teachingPoints;legos)}*
limit*{integer}*
offset*{integer}*
search*{status.id:_statusId;owner.email:_email;teachingPoints.id:_teachingPointId;legos.name:_legoName}*
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /boxes/{id}
**Http method:** GET
**Description:** Display the specified Box
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /boxes
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /boxes/{id}?_method=PUT
**Http method:** POST
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

**IMPORTANT:** Note this update method is set to POST, not to PUT, and is required to send the parameter _method=PUT because of a bad behavior when uploading files using method PUT. In the box update is possible to upload a pdf file

##### Delete
**name:** destroy
**path:** /boxes/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### Lego 
##### List
**name:** index
**path:** /legos
**Http method:** GET
**Description:** Get a listing of the Legos.
**Optional parameters:** 
with*{semicolon relationships(status;type;createdBy;owner;boxes;files;fileRequests)}*
limit*{integer}*
offset*{integer}*
search*{name:_name;owner.email:_email;status.name:_statusName;status.id:_statusId}*
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /legos/{id}
**Http method:** GET
**Description:** Display the specified Lego
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /legos
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /legos/{id}
**Http method:** PUT
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /legos/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### File
##### List
**name:** index
**path:** /files
**Http method:** GET
**Description:** Get a listing of the Files.
**Optional parameters:** 
with*{semicolon relationships(type;createdBy;fileable;legos;fileRequest)}*
limit*{integer}*
offset*{integer}*
search*{name:_name;createdBy.email:_email;type.name:_typeName;type.id:_typeId;placeholder:_placeholder(boolean)}*
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /files/{id}
**Http method:** GET
**Description:** Display the specified File
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /files
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /files/{id}?_method=PUT
**Http method:** POST
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

**IMPORTANT:** Note this update method is set to POST, not to PUT, and is required to send the parameter _method=PUT because of a bad behavior when uploading files using method PUT

##### Delete
**name:** destroy
**path:** /files/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

#### File Request
##### List
**name:** index
**path:** /fileRequests
**Http method:** GET
**Description:** Get a listing of the File Requests.
**Optional parameters:** 
with*{semicolon relationships(status;createdBy;files;legos)}*
limit*{integer}*
offset*{integer}*
search*{status.id:_statusId;type.id: _typeId;createdBy.email:_email;description:_description}*
searchFields
filter
orderBy*{string}*
sortedBy*{string(default asc)}*
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Show
**name:** show
**path:** /fileRequests/{id}
**Http method:** GET
**Description:** Display the specified File Request
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Persist
**name:** store
**path:** /fileRequests
**Http method:** POST
**Description:** Store Entity
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Update
**name:** update
**path:** /fileRequests/{id}
**Http method:** POST
**Description:** Update Entity
**Parameter:** Entity id
**Parameter:** Request object with entity fillable attributes
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string

##### Delete
**name:** destroy
**path:** /fileRequests/{id}
**Http method:** DELETE
**Description:** Delete Entity
**Parameter:** Entity id
**Response:** Json object with structure *success:* boolean, *data:* array, *message:* string
