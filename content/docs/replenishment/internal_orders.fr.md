+++
title = "Commandes Internes"
description = "Commander chez des fournisseurs utilisant mSupply."
date = 2022-03-19T18:20:00+00:00
updated = 2022-03-19T18:20:00+00:00
draft = false
weight = 2
sort_by = "weight"
template = "docs/page.html"

[extra]
toc = true
top = false
+++

Les commandes internes portent plusieurs autres noms dans certains pays ou systèmes :

- Réquisitions
- Commandes
- Rapports Commande

Les commandes internes sont un moyen qui permet aux utilisateurs d'adresser une commande à l'endroit d'un autre dépôt.

## Voir les Commandes Internes

Pour adresser une commande à un fournisseur:

1. Allez dans le menu `Approvisionnement`
2. Cliquez sur `Commandes internes`

![Internal Order: nav](/docs/replenishment/images/intord_access_fr.png)

Une liste de commandes internes s'affiche à l'écran:

![Internal Order: list](/docs/replenishment/images/intord_list_fr.png)

Vous pouvez utiliser le champs `Search by comment` pour filter la liste par commentaire:

![Internal Order: filter by comment](/docs/replenishment/images/intord_filterlistbycomment.gif)

Vous pouvez trier la liste à l'aide des en-têtes de colonne :

1. Appuyez sur l'en-tête de la colonne que vous souhaitez trier. La colonne est triée par ordre croissant.
2. Appuyez à nouveau sur l'en-tête, la colonne sera triée dans l'ordre inverse.

## Créer une nouvelle commande interne

### Sélectionner un fournisseur

1. Cliquez sur le bouton `Nouvelle Commande` (dans le coin supérieur droit):

![Internal Order: new order](/docs/replenishment/images/intord_newreqbutton_fr.png)

2. Une nouvelle fenêtre vous invitant à choisir un fournisseur s'ouvre:

![Internal Order: select supplier](/docs/replenishment/images/intord_selectsupplier2_fr.png)

3. Sélectionnez un fournisseur en cliquant sur son nom. Vous verrez une fenêtre comme celle-ci :

![Internal Order: newly created order](/docs/replenishment/images/intord_newintord_fr.png)

### Defining Maximum Month of Stock (Maximum MOS)

Defining the Maximum MOS (Month of Stock) is critical to the calculation of the **Suggested Quantity** and you can change it:

- There is an industry rule of thumb that the _Maximum MOS_ should be set to 3 times the ordering cycle
- The default _Maximum MOS_ is `3.0`, which is based on a monthly ordering cycle
- If for example, the ordering cycle was every two months, then _Maximum MOS_ should be set to 3 x 2 = `6.0`

<div class="imagetitle">
In below example, we are setting our Maximum MOS to 3 Months.  
</div>

![MaxMOS](/docs/replenishment/images/intord_maxmos.png)

This can be done before or after adding items to your order.

### Adding a single item

Tap on `Add Item` to add a single item to your order. A new window opens:

![Internal Order: add item](/docs/replenishment/images/intord_additem2.png)

First select the item you want to add to your order. Open the `Stock details` dropdown menu and select your item from the list. You can also type some or all of an item name (or code) to look for a specific item.

Once item is selected, you should see the following information on the window:

- **Item Code** and **Item Name**
- **Unit**: the default unit used for this item (_eg. Tablet, Vial_)
- **AMC**: Average Monthly Consumption. How much stock your store uses each month on average (based on a configurable number of months, default is set to 3 months)
- **Suggested Quantity**: how much stock mSupply suggests that your order to reach your stock target quantity
- **Order quantity**: the quantity of units that you request from your supplier

You should also see the following charts:

- **Stock distribution**: In this chart, you will see the following information:
  - The _Target Quantity_ for the item. This is calculated as: Maximum MOS x AMC.
  - Your current _Stock on Hand_ (in grey)
  - The _suggested quantity_ calculated by mSupply

<div class="imagetitle">
In below example, our target quantity is 600 units which is the equivalent of 3 months of stock (3 x 200 = 600 units). Our stock on hand (in grey) is 50 so in order to reach my target, mSupply suggests to order 550 units (600 - 50). 
</div>

![Stock Distribution](/docs/replenishment/images/intord_charts_stockdistri.png)

<div class="imagetitle">
In below example, the target quantity is 62 units. Since we already have 250 units in stock (in grey), the suggested quantity is zero. 
</div>

![Stock Distribution 2](/docs/replenishment/images/intord_charts_stockdistri2.png)

- **Consumption History (monthly)**: this chart shows the monthly consumption up to 12 months in the past (in grey) and the current AMC (in orange):

![Consumption](/docs/replenishment/images/intord_charts_consumption.png)

- **Stock Evolution**: this chart shows you your stock level for the last 30 days and your projected inventory for the next 30 days. The projected stock will be updated based on your inputs in the `Order quantity` field:

![Stock Evolution](/docs/replenishment/images/intord_charts_stockevolution.png)

### Adding items using a master list

If your organisation is using Master Lists, you can add multiple items at once using your store's master lists. It is particularly useful when you have a lot of items in your order and you don't want to add them all one by one.

1. Tap on the `Add from master list` button
2. Select a master list
3. A dialog window opens asking you whether you want to add all of the items from this master list. Tap `OK` if you wish to proceed.

All the items of the master list are now listed in your order. If you had previously added single item, it will add items that are not already there.

Tap on an order line to change the **Order Quantity** or tap on the button `Requested to Suggested` button

![Internal Order: add from master list](/docs/replenishment/images/intord_addfromml.gif)

<div class="remarque"> 
Master Lists are defined and assigned to stores at the central server level. You can only see the master lists that are visible to your store. 
<br> <br>
If you don't find the master list you are looking for and if you want to create a new one, please contact your administrator.
</div>

<div class="conseil">
You can create Internal Orders from multiple master lists by repeating above actions with another master list. 
</div>

### Reading the Internal Order's list

When you add items (using a master list or not), the item is added to the order's table. The following information is provided for each order line:

| Status                   | Description                                                                                                                                        |
| :----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Code**                 | Code of the item                                                                                                                                   |
| **Name**                 | Name of the item                                                                                                                                   |
| **SoH (Est. remaining)** | How much stock currently available in your store for this store                                                                                    |
| **AMC**                  | Average Monthly Consumption: how much stock your store uses each month on average (based on a configurable number of months, defaults to 3 months) |
| **Target Stock**         | This is the stock you are aiming for. Calculated as: AMC x Maximum MOS                                                                             |
| **Suggested Quantity**   | How much stock mSupply suggests that your order. This is calculated as: AMC x Maximum MOS - SoH                                                    |
| **Requested**            | This is set to zero by default. This is the quantity of units you are ordering from your supplier.                                                 |
| **Comment**              | A comment for the order line. Comments will be visible to your supplier.                                                                           |

### Using Suggested Quantities

If you tap on the `Use Suggested Quantities` on the requisition header, mSupply will automatically copy the values in the **Suggested Quantity** column into the **Requested Quantity** column.

You can always manually edit the order quantity for each by tapping on an order line.

![Use Suggested Quantities](/docs/replenishment/images/intord_reqtosug.png)

### Printing an Internal Order

When viewing a specific Internal Order, simply click the `Print` button which is on the top right of the page.
When printing, a PDF file is generated for you, which will then open in a new browser tab. This can then be printed using your browser by clicking print or using `control`+`P` (if using windows) or `cmd`+`P` keys on your keyboard (if using a mac).

![Print button](/docs/introduction/images/print_button.png)

This will either

- Show a menu of possible reports for you to select from before creating a PDF. This will happen if there are more than one report defined for the `Requisition` report type.
- Create a PDF immediately, if there is only one report to select from

![Print menu](/docs/distribution/images/os_print_menu.png)

### Sending an Internal Order

To send the order to your supplier:

1. Tap on the `Confirm Sent` button (bottom right corner)
2. A dialog window opens asking you whether you are sure to want to send the order. Tap on `OK` to proceed
3. Status of your order is now `SENT` and the order is no longer editable

<div class="avertissement">
Ensure that your order is correct before sending it to your supplier. Once sent, no further changes can be made to finalised orders. 
</div>
