---
layout: "oci"
page_title: "OCI: oci_database_autonomous_data_warehouse"
sidebar_current: "docs-oci-resource-database-autonomous_data_warehouse"
description: |-
  Creates and manages an OCI AutonomousDataWarehouse
---

# oci_database_autonomous_data_warehouse
The `oci_database_autonomous_data_warehouse` resource creates and manages an OCI AutonomousDataWarehouse

Creates a new Autonomous Data Warehouse.


## Example Usage

```hcl
resource "oci_database_autonomous_data_warehouse" "test_autonomous_data_warehouse" {
	#Required
	admin_password = "${var.autonomous_data_warehouse_admin_password}"
	compartment_id = "${var.compartment_id}"
	cpu_core_count = "${var.autonomous_data_warehouse_cpu_core_count}"
	data_storage_size_in_tbs = "${var.autonomous_data_warehouse_data_storage_size_in_tbs}"
	db_name = "${var.autonomous_data_warehouse_db_name}"

	#Optional
	defined_tags = {"Operations.CostCenter"= "42"}
	display_name = "${var.autonomous_data_warehouse_display_name}"
	freeform_tags = {"Department"= "Finance"}
	license_model = "${var.autonomous_data_warehouse_license_model}"
}
```

## Argument Reference

The following arguments are supported:

* `admin_password` - (Required) (Updatable) A strong password for Admin. The password must be between 12 and 60 characters long, and must contain at least 1 uppercase, 1 lowercase and 2 numeric characters. It cannot contain the double quote symbol ("). It must be different than the last 4 passwords.
* `compartment_id` - (Required) The [OCID](https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/identifiers.htm) of the compartment of the Autonomous Data Warehouse.
* `cpu_core_count` - (Required) (Updatable) The number of CPU Cores to be made available to the database.
* `data_storage_size_in_tbs` - (Required) (Updatable) Size, in terabytes, of the data volume that will be created and attached to the database. This storage can later be scaled up if needed. 
* `db_name` - (Required) The database name. The name must begin with an alphabetic character and can contain a maximum of 14 alphanumeric characters. Special characters are not permitted. The database name must be unique in the tenancy.
* `defined_tags` - (Optional) (Updatable) Defined tags for this resource. Each key is predefined and scoped to a namespace. For more information, see [Resource Tags](https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/resourcetags.htm).  Example: `{"Operations.CostCenter": "42"}` 
* `display_name` - (Optional) (Updatable) The user-friendly name for the Autonomous Data Warehouse. The name does not have to be unique.
* `freeform_tags` - (Optional) (Updatable) Free-form tags for this resource. Each tag is a simple key-value pair with no predefined name, type, or namespace. For more information, see [Resource Tags](https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/resourcetags.htm).  Example: `{"Department": "Finance"}` 
* `license_model` - (Optional) The Oracle license model that applies to the Oracle Autonomous Data Warehouse. The default is BRING_YOUR_OWN_LICENSE. 


** IMPORTANT **
Any change to a property that does not support update will force the destruction and recreation of the resource with the new property values

## Attributes Reference

The following attributes are exported:

* `compartment_id` - The [OCID](https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/identifiers.htm) of the compartment.
* `connection_strings` - The connection string used to connect to the Data Warehouse. The username for the Service Console is ADMIN. Use the password you entered when creating the Autonomous Data Warehouse for the password value.
	* `all_connection_strings` - All connection strings used to connect to the Data Warehouse. The username for the Service Console is ADMIN. Use the password you entered when creating the Autonomous Data Warehouse for the password value.
	* `high` - The High database service provides the highest level of resources to each SQL statement resulting in the highest performance, but supports the fewest number of concurrent SQL statements.
	* `low` - The Low database service provides the least level of resources to each SQL statement, but supports the most number of concurrent SQL statements.
	* `medium` - The Medium database service provides a lower level of resources to each SQL statement potentially resulting a lower level of performance, but supports more concurrent SQL statements.
* `cpu_core_count` - The number of CPU cores to be made available to the database.
* `data_storage_size_in_tbs` - The quantity of data in the database, in terabytes.
* `db_name` - The database name.
* `db_version` - A valid Oracle Database version for Autonomous Data Warehouse.
* `defined_tags` - Defined tags for this resource. Each key is predefined and scoped to a namespace. For more information, see [Resource Tags](https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/resourcetags.htm).  Example: `{"Operations.CostCenter": "42"}` 
* `display_name` - The user-friendly name for the Autonomous Data Warehouse. The name does not have to be unique.
* `freeform_tags` - Free-form tags for this resource. Each tag is a simple key-value pair with no predefined name, type, or namespace. For more information, see [Resource Tags](https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/resourcetags.htm).  Example: `{"Department": "Finance"}` 
* `id` - The [OCID](https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/identifiers.htm) of the Autonomous Data Warehouse.
* `license_model` - The Oracle license model that applies to the Oracle Autonomous Data Warehouse. The default is BRING_YOUR_OWN_LICENSE. 
* `lifecycle_details` - Additional information about the current lifecycle state.
* `service_console_url` - The URL of the Service Console for the Data Warehouse.
* `state` - The current state of the database.
* `time_created` - The date and time the database was created.

## Import

AutonomousDataWarehouses can be imported using the `id`, e.g.

```
$ terraform import oci_database_autonomous_data_warehouse.test_autonomous_data_warehouse "id"
```
