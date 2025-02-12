---
subcategory: "CDN"
layout: "azurerm"
page_title: "Azure Resource Manager: azurerm_cdn_frontdoor_rule_set"
description: |-
  Manages a CDN FrontDoor Rule Set.
---

# azurerm_cdn_frontdoor_rule_set

Manages a CDN FrontDoor Rule Set.

## Example Usage

```hcl
resource "azurerm_resource_group" "example" {
  name     = "example-cdn-frontdoor"
  location = "West Europe"
}

resource "azurerm_cdn_frontdoor_profile" "example" {
  name                = "example-profile"
  resource_group_name = azurerm_resource_group.example.name
  sku_name            = "Standard_AzureFrontDoor"

}

resource "azurerm_cdn_frontdoor_rule_set" "example" {
  name                     = "ExampleRuleSet"
  cdn_frontdoor_profile_id = azurerm_cdn_frontdoor_profile.example.id
}
```

## Arguments Reference

The following arguments are supported:

* `name` - (Required) The name which should be used for this CDN FrontDoor Rule Set. Changing this forces a new CDN FrontDoor Rule Set to be created.

* `cdn_frontdoor_profile_id` - (Required) The ID of the CDN FrontDoor Profile. Changing this forces a new CDN FrontDoor Rule Set to be created.

## Attributes Reference

In addition to the Arguments listed above - the following Attributes are exported:

* `id` - The ID of the CDN FrontDoor Rule Set.

## Timeouts

The `timeouts` block allows you to specify [timeouts](https://www.terraform.io/language/resources/syntax#operation-timeouts) for certain actions:

* `create` - (Defaults to 30 minutes) Used when creating the CDN FrontDoor Rule Set.
* `read` - (Defaults to 5 minutes) Used when retrieving the CDN FrontDoor Rule Set.
* `delete` - (Defaults to 30 minutes) Used when deleting the CDN FrontDoor Rule Set.

## Import

CDN FrontDoor Rule Sets can be imported using the `resource id`, e.g.

```shell
terraform import azurerm_cdn_frontdoor_rule_set.example /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resourceGroup1/providers/Microsoft.Cdn/profiles/profile1/ruleSets/ruleSet1
```
