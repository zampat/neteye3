# Clean connections to computer models different or changed from racks model

Condition:
Computer model ID is different from Racks model id item registered to the positon on row.
Problem:
The row is not shown in list

Racks without valid model:
SELECT RI.*
FROM `glpi_plugin_racks_itemspecifications` RI
WHERE RI.itemtype = "ComputerModel" and RI.model_id not in (SELECT M.id
FROM `glpi_computermodels` M )

Racks items where computer model is different from racks item model id:

SELECT RI.*, C.computermodels_id AS CompModel, RS.model_id AS RSmodel
FROM `glpi_plugin_racks_racks_items` RI
JOIN `glpi_computers` C ON RI.items_id = C.id
JOIN glpi_plugin_racks_itemspecifications RS ON RS.id = RI.plugin_racks_itemspecifications_id
WHERE C.computermodels_id <> RS.model_id and RI.position = 31 and plugin_racks_racks_id = 23

SAFE DELETE:
DELETE RI
FROM glpi_plugin_racks_racks_items AS RI
JOIN `glpi_computers` C ON RI.items_id = C.id
JOIN glpi_plugin_racks_itemspecifications RS ON RS.id = RI.plugin_racks_itemspecifications_id
WHERE C.computermodels_id <> RS.model_id and RI.position = 31 and plugin_racks_racks_id = 23

Clean up:
DELETE RI
FROM glpi_plugin_racks_racks_items AS RI
JOIN `glpi_computers` C ON RI.items_id = C.id
JOIN glpi_plugin_racks_itemspecifications RS ON RS.id = RI.plugin_racks_itemspecifications_id
WHERE C.computermodels_id <> RS.model_id
