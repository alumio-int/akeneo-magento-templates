# Synchronization of Akeneo Families and Attributes into Magento 2 Attribute Sets and Attributes

The data flow between systems is as follows:
* Create or update family, attribute and attribute options at Akeneo
    * Family at Settings → Families
    * Attribute at Settings → Attributes
       (Please note that the attributes will need to be connected to the family in order to be sent to Magento 2)
    * Attribute options at the Attribute detail which type are simple select and multi select.
    * Reference entity records will also become attribute options for the attribute type Akeneo Reference Entity and Akeneo Reference Entity Collection.
* Alumio catches the change from the Incoming **"Akeneo - Fetch - Families and Attributes"** and creates a task.
* Alumio then check Magento 2 for already created attributes to avoid duplications.
* Alumio processed the task data to be suited to Magento using the Outgoing **"Magento 2 - Send - Attribute Sets and Attributes"**.
* You can check the sync in Magento 2 as 
    * Magento 2 Attribute Set (Store → Attributes → Attribute Set)
    * Magento 2 Attribute (Store → Attributes → Product)

For more information please refer to this wiki [page](https://github.com/alumio-int/akeneo-magento-templates/wiki/Synchronization-of-Akeneo-Families-and-Attributes-into-Magento-2-Attribute-Sets-and-Attributes).