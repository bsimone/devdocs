---
group: release-notes
title: Commerce B2B Release Notes
---

The release notes for the B2B extension captures additions and bug fixes that Magento has added during a release cycle.
These release notes can include:

-  {:.new} New features
-  {:.fix} Fixes and improvements

## Magento B2B - Version 1.3.2

-  {:.fix} <!--- MC-39862--> Magento now successfully sends update emails about expired negotiable quotes. Previously, when a negotiable quote expired, Magento did not send update emails.

-  {:.fix} <!--- MC-40682--> Magento now successfully sends update emails about soon-to-expire and expired negotiable quotes when a `cron` job is missing.

### Company

-  {:.fix} <!--- MC-41542--> The Create New Company Account page country dropdown field no longer lists empty option values. Previously, the first two option values and the country code `AN` were empty.

-  {:.fix} <!--- MC-41260--> Clicking on the **Return** button for an order that was created by a company user now redirects an administrative user to the Create Return page as expected. Previously, the administrator was redirected to the Order History page.

-  {:.fix} <!--- MC-40798--> Magento no longer fails with an out-of-memory error when executing the `app/code/Magento/PurchaseOrder/Setup/Patch/Data/InitPermissions.php::apply` method during `bin/magento setup:upgrade`.  Previously, Magento did not use batch size for collection when initializing permissions, but instead loaded a collection of all company roles.

-  {:.fix} <!--- MC-40551--> Company users can now edit and update customer custom attribute values. Previously, these attributes did not bind properly with the create and edit user form. A company user could enter different attribute values, but Magento did not save these values correctly.

-  {:.fix} <!--- MC-32653--> The resource tree for company role permissions can now be translated as expected. Previously, the permissions tree was not translated even though valid translation files were present.

-  {:.fix} <!--- MC-40358--> Magento now saves custom customer attribute values for B2B users as expected. Previously, creating a company account that contained custom customer attributes triggered a template error, and Magento did not successfully load the form. Adding an argument to the layout of `company_create_account` resolved this issue.

-  {:.fix} <!--- MC-41721--> Company user filters such as Show All Users, Show Active Users, and Show Inactive Users now work as expected. Previously, filtering actions on the company user page caused a JavaScript error.

### Company credit

-  {:.fix} <!--- MC-41551--> Administrators with restricted accounts that include only website-level privileges can now create a company that uses a different currency than the website.

-  {:.fix} <!--- MC-41523--> Magento now sends company emails from the correct `from` email address and scope. Previously, Magento did not consider website scope when sending company credit assignment or update email.

### Quick Order

-  {:.fix} <!--- MC-42104--> Creating an order using Quick Order from a CSV file now works as expected with nonexistent SKUs.

-  {:.fix} <!--- MC-40268--> Using Quick Order to search on multiple SKUs now works as expected. Previously, results included duplicate entries.

-  {:.fix} <!--- MC-40261--> The Added Product list display now treats SKUs entered in lowercase and uppercase the same when you use SKUs to select multiple products during Quick Order.

-  {:.fix} <!--- MC-40225--> Using Quick Order now adds products in the quantity specified by the shopper. Previously, Magento added one product only even when a shopper specified quantities that exceeded one.

-  {:.fix} <!--- MC-41283--> The Quick Order autocomplete feature now works with partial SKUs.

-  {:.fix} <!--- MC-41299--> Magento now displays products that have been configured as **Not visible individually** on the Quick Order page’s auto-suggest list and search results.

-  {:.fix} <!--- MC-42402--> Shoppers can now use the Quick Order form to add multiple products by SKUs that include upper-case characters. Previously, only the first product was added.

### Negotiable quote

-  {:.fix} <!--- MC-41232--> Shoppers are now redirected to the negotiable quote page after pasting the link to a negotiable quote in the URL field and successfully logging in. Previously, shoppers were redirected to the My Account page.

-  {:.fix} <!--- MC-39317--> Re-ordering now works as expected for orders that contain a product with a Date Customizable Option for a customer account that was created during checkout. Previously, Magento did not process the re-order and displayed this error: `The product has required options. Enter the options and try again`.

-  {:.fix} <!--- MC-39063--> The shipping address for a negotiable quote is no longer editable during checkout when the Purchase Order module is disabled. This behavior resulted from a previous fix in which `isQuoteAddressLocked` was removed from the negotiable quote checkout renderer.

-  {:.fix} <!--- MC-38967--> Merchants can now add products to a negotiable quote from the Admin.

### Purchase orders

-  {:.fix} <!--- MC-39983--> Magento now displays an informative error message as expected when you place a purchase order using Paypal Express Checkout when the **Name Prefix** attribute is set to **required**. Previously, Magento did not place the order or display an error message. [GitHub-552](https://github.com/magento/partners-magento2b2b/issues/552)

-  {:.fix} <!--- MC-39620--> The UI component for the billing address in the Purchase Order module now uses quote address correctly when Google Tag Manager is enabled. Previously, a JavaScript error occurred on the payment page.

### Requisition lists

-  {:.fix} <!--- MC-40426--> Merchants can now use the POST `rest/all/V1/requisition_lists` endpoint to create a requisition list for a customer. Previously, Magento threw this 400 error when you tried to create a requisition list: `Could not save Requisition List`.

-  {:.fix} <!--- MC-41123--> The **Add to Requisition List** button now appears for a shopping cart’s in-stock products when the cart also contains out-of-stock products. Previously, if a cart contained two products, one of which was out-of-stock, the **Add to Requisition List** button did not appear for either products.

-  {:.fix} <!--- MC-40877--> You can now use the REST API to add a product to a requisition list.

-  {:.fix} <!--- MC-40155--> Requisition list **Latest Activity Date** values now adhere to locale format.

-  {:.fix} <!--- MC-39580--> Magento no longer throws a fatal error when you edit a bundle product from a requisition list.

-  {:.fix} <!--- MC-40454--> Magento now displays the correct product price when you add a product with a customizable option `(File)` to a wish list from a requisition list. The link to the uploaded file is also visible as expected. Previously, Magento displayed incorrect product prices and did not display the link to the file.

-  {:.fix} <!--- MC-36383--> Products with a customizable option `(File)` can now be added to a shopping cart from a requisition list. [GitHub-377](https://github.com/magento/partners-magento2b2b/issues/377)

### Shared catalog

-  {:.fix} <!--- MC-40497--> An administrator with a role limited to a specific website can now create, view, and edit a shared catalog. Previously, Magento threw a fatal error when an administrator with a limited role tried to create a shared catalog.

-  {:.fix} <!--- MC-41337--> Layered navigation results now include an accurate count of products with filtered attributes, and shoppers can now apply multiple filters. Previously, only one filter could be applied, and Magento displayed an inaccurate product count in layered navigation.

-  {:.fix} <!--- MC-40779--> Magento now correctly displays product counts in layered navigation filters in search results. Previously, a plugin for the Search Results page did not use ElasticSearch but issued a new query to the database.

-  {:.fix} <!--- MC-39978--> Magento no longer deletes tier prices when a merchant deletes all products from a default shared catalog.

-  {:.fix} <!--- MC-39802--> Filters are now filtered by the current category and displayed correctly on all pages when shared catalogs are enabled. Previously, filters were wrongly calculated for the current page only and were not filtered by the current category.

-  {:.fix} <!--- MC-39522--> The GraphQL `products` query no longer returns  a product’s price range and category for products that are not assigned to a shared catalog when shared catalog is enabled. Previously, the query returned the product’s aggregations, even though the product itself was not returned in the `items` array.

## Magento B2B - Version 1.3.1

-  {:.new} Online payment methods are now supported for purchase orders.

-  {:.fix} Adding a configurable product to the shopping cart directly from a requisition list when this product was used in a prior order no longer returns a system error. [GitHub-302](https://github.com/magento/partners-magento2b2b/issues/302)

-  {:.fix} Magento now displays the Requires My Approval tab correctly for purchase orders when a split database configuration is deployed. [GitHub-259](https://github.com/magento/partners-magento2b2b/issues/259)

-  {:.fix} Magento now displays details about bundle products and gift card when you view purchase orders. [GitHub-213](https://github.com/magento/partners-magento2b2b/issues/213)

-  {:.fix} Shoppers are now redirected as expected after logging into their account while browsing in a store where **Website Restriction** is enabled and **Restriction Mode** is set to **Private Sales: Login Only**. Previously, shoppers were redirected to the store home page. <!--- MC-38934-->

-  {:.fix} Order history now loads as expected in a company administrator's My account page in deployments with a B2B company hierarchy that contains many customers (greater than 13000). Previously, order history loaded very slowly or not at all, and Magento displayed a 503 error. <!--- MC-38830-->

-  {:.fix} Magento no longer displays multiple identical warning messages when you add an unconfigured product with customizable options to a Requisition List from a Category page. <!--- MC-38342-->

-  {:.fix} New and duplicated products are now visible as expected on the category page when B2B shared catalogs are enabled. <!--- MC-38307-->

-  {:.fix} Magento now maintains the correct `store_id` that is associated with a company administrator when the customer group for a company is updated. Previously, the `store_id` changed to the default store when the group was updated. <!--- MC-38196-->

-  {:.fix} Magento now saves a grouped product to a requisition list as a list of simple products in the same way as it adds a grouped product to a shopping cart. Previously, due to how Magento saved grouped products, the link for a grouped product from the requisition list always redirected to simple products and not to the grouped product. <!--- MC-38049-->

-  {:.fix} You can now filter orders by the **Company Name** field when exporting order information in CSV format. Previously, Magento logged an error in `var/export/{file-id}`. <!--- MC-37785-->

-  {:.fix} Magento now displays the Create Requisition List popup as expected when you select the Create New Requisition List tab on the storefront. <!--- MC-37915-->

-  {:.fix} Requisition lists now include all grouped products and quantities that have been added to the list. Previously, when a merchant navigated to a requisition list after adding products to it from a product detail page, Magento displayed this error: `1 product(s) require your attention - Options were updated. Please review available configurations`. [GitHub-59](https://github.com/magento/partners-magento2b2b/issues/59) <!--- MC-37621-->

-  {:.fix} The correct store view is now associated with the relevant website when you create a new company in a multi-site deployment. Previously, you could not create a company, and Magento displayed this error: `The store view is not in the associated website`. <!--- MC-37488-->

-  {:.fix} Ordering products by SKU using Quick Order no longer results in duplicate product quantities in the CSV file. <!--- MC-37427-->

-  {:.fix} The **Add to Cart** button is no longer blocked when the Enter Multiple SKUs section of the Quick Order page contains an empty value. Instead, Magento now displays a message prompting you to enter valid SKUs. <!--- MC-37387-->

-  {:.fix} Magento now displays this message on the product page when you submit a product review from a requisition list: `You submitted your review for moderation`. The review also appears on the Pending Reviews page (Admin **Marketing** > **Pending Reviews**). Previously, although Magento added the review to the list of pending reviews, it threw a 404 error on the product page. <!--- MC-37119-->

-  {:.fix} The performance of the `sharedCatalogUpdateCategoryPermissions` consumer has been improved. After creating a shared catalog, the catalog permission indexer now uses only the customer group ID from the shared catalog, not all customer groups. <!--- MC-36770-->

-  {:.fix} Custom customer address attribute fields that are associated with a shopper’s non-default address are now saved as expected in the storefront checkout workflow. <!--- MC-36630-->

-  {:.fix} Orders for products that belong to a store’s default shared catalog can now be placed for shoppers through the Admin REST API (`rest/V1/carts/{{CART_ID}}/items`) as expected. Magento now checks if the product was assigned to a public catalog before shared catalog permissions validation in `\Magento\SharedCatalog\Plugin\Quote\Api\ValidateAddProductToCartPlugin::beforeSave`. Previously, Magento did not add the product to the shopper’s cart and threw this error: `No such shared catalog entity`. <!--- MC-36535-->

-  {:.fix} Magento now sends new company user registration emails from the Magento store's address. Previously, this email was sent from the company administrator’s address. <!--- MC-36480-->

-  {:.fix} Magento now checks custom attributes for duplication of reserved company attribute names before permitting a merchant to save a new attribute. <!--- MC-36282-->

-  {:.fix} The `credit_history` query now returns the specified company’s credit history for both the originally allocated amount and the purchased amount. Previously, this query returned an error. [GitHub-29990](https://github.com/magento/magento2/issues/29990)

-  {:.fix} The **Company** and  **Job Title** fields on the Edit Account Information page are no longer editable. [GitHub-312](https://github.com/magento/partners-magento2b2b/issues/312)

### B2B known issues

**Issue**: B2B buyers can use online payment methods to bypass the usual purchase order flow. This scenario can occur if the buyer can reduce their entire checkout total to a 0 — for example, by a promo code or gift card —  and subsequently remove the code or gift card. Even under those conditions, Magento still places the order for the correct amount based on the prices of the items in their assigned catalog. **Workaround**: Disable gift cards and coupon codes when online payment methods are enabled for purchase order approval. <!--- B2B-1603-->

**Issue**: Buyers are redirected to the shopping cart when trying to place an order from a purchase order using PayPal Express Checkout when **In-Context Mode** is disabled. <!--- B2B-1604-->

**Issue**: Magento sometimes displays a 404 error when a buyer creates a purchase order and then navigates to the checkout page. This error occurs when a buyer has previously created a different purchase order with an online payment method before navigating to the checkout page without completing the previous purchase. The buyer can still place the purchase order. **Workaround**: None. <!--- B2B-1605-->

**Issue**: Discounts for a specific payment method persist during checkout for a purchase order even when the buyer changes their payment method during final checkout. As a result, customers may receive a discount that they are not entitled to. This occurs because a cart rule for the original payment method is still applied despite the change in payment method. **Workaround**: None. See the [Magento 2.4.2 B2B known issue: discount remains for online Purchase Orders after payment method is changed](https://support.magento.com/hc/en-us/articles/360054667312) Knowledge Base article. <!-- B2B-1012 -->

**Issue**: The `deleteRequisitionListOutput` query returns details about the deleted requisition list instead of the remaining requisition lists. <!--- MC-39894-->
## Magento B2B - Version 1.3.0

This release includes improvements to order approvals, shipping methods, shopping cart, and logging of Admin actions.

-  {:.new} B2B order approvals have been enhanced to improve usability and to allow for bulk actions on purchase orders.

-  {:.new} B2B merchants can now control shipping methods that are offered to each Company.<!--- BUNDLE-160 161 162 -->

-  {:.new} Merchants can now allow users to clear the contents of their shopping cart in a single action and can configure this ability independently on each website <!--- BUNDLE-108 -->

-  {:.new} B2B buyers can now add individual items or the entire contents of their shopping cart directly to a requisition list. <!--- BUNDLE-145 144-->

-  {:.new} B2B merchants can create orders from the Admin on behalf of customers using Payment on Account as the payment method. <!--- BUNDLE-166 178-->

-  {:.new} Merchants can now directly view all quotes associated with a user from the customer’s detail page. <!--- BUNDLE-139 -->

-  {:.new} Merchants can now filter the Customers Now Online grid by Company. <!--- BUNDLE-137 -->

-  {:.new} Admins can now filter customers in the Admin by Sales Rep. <!--- BUNDLE-110 -->

-  {:.new} To reduce creation of fraudulent or spam accounts, merchants can now enable Google reCAPTCHA on the New Company Request form on the storefront. <!--- BUNDLE-154 -->

-  {:.new} Admin actions taken in the Company modules are now logged in the Admin Actions Log. Actions are logged from all relevant company modules: `Company`, `NegotiableQuote`, `CompanyCredit`, `SharedCatalog`.  <!--- BUNDLE-180 181 182 183 -->

-  {:.fix} Magento no longer displays the **Delete customer** button on the **Customers** page when the logged-in administrator does not have rights to delete customers in deployments where B2B is installed. <!--- MC-35655-->
-  {:.fix} Customer group is no longer automatically changed for a customer who is assigned to a Company when you edit the customer on the Customer grid. <!--- MC-35254-->

-  {:.fix} When a merchant creates a new shared catalog, permissions are now automatically set to **Allow** for the **Display Product Prices** and **Add to Cart** features in categories when the customer group has been assigned this access in catalog permission settings. Previously, these settings were automatically set to **Deny** even when catalog permissions were set to **Allow**.<!--- MC-34792-->

-  {:.fix} Shared catalog category permissions are no longer overwritten when a product is edited from the product edit page.<!--- MC-34777-->

-  {:.fix} Magento now sends an email notification confirming that a customer has permission to exceed the designated credit limit when a merchant enables the **Allow To Exceed Credit Limit** setting. Previously, the notification email sent by Magento indicated that the customer did not have permission to exceed the limit. <!--- MC-34584-->

-  {:.fix} The HTML container that surrounds product price on requisition lists is now rendered correctly for the children of bundled products. <!--- MC-36331-->

-  {:.fix} Merchants can now designate the language in which company user email is sent when creating a new company in multi-language deployments. Previously, the drop-down menu the enables merchants to select the appropriate store view and language was not displayed.  <!--- MC-35777-->

-  {:.fix} Custom customer address attributes fields are now displayed as expected in the storefront checkout workflow. <!--- MC-35607-->

-  {:.fix} The B2B Features tab (Admin **Stores** > **Configuration** > **General** ) now opens correctly. <!--- MC-35458-->Guests can now use QuickOrder to add products to their cart and then successfully remove items. Previously, when a shopper used QuickOrder to add multiple products to their cart, and then removed a product, the product was not removed. <!--- MC-35327-->

-  {:.fix} A company can now be updated using the REST API PUT `/V1/company/:companyId` request without specifying the `region_id` when state is configured as **not required**. Previously, even though `region_id` was not required, Magento threw an error if it was not specified. <!--- MC-35304-->

-  {:.fix} When you create or update a B2B Company using the REST API (`http://magento.local/rest/V1/company/2`, where `2` represents the company ID), the response now includes the settings for `applicable_payment_method` or `available_payment_methods` as expected. <!--- MC-35248-->

-  {:.fix} Magento no longer displays a 404 page when a merchant uses the **Enter** button instead of clicking the **Save** button when creating a requisition list on the storefront.<!--- MC-35094-->

-  {:.fix} Category permissions no longer change when a new product is assigned to a public shared catalog. Previously, category permissions were duplicated. <!--- MC-34386-->

-  {:.fix} The REST API endpoint PUT `rest/default/V1/company/{id}`, which is used to update Company email, is no longer case-sensitive. <!--- MC-34308-->

-  {:.fix} Disabling reward modules no longer affects B2B features on customer accounts. Previously, when reward modules were disabled, the following B2B-related tabs were not displayed: Company Profile, Company Users, and Roles and Permissions.<!--- MC-34191-->

-  {:.fix} Magento now uses the correct sender name on email notifications when changes are made to company accounts. Previously, Magento used the general contact sender name defined in the default scope for all emails. <!--- MC-33917-->

-  {:.fix} You can now successfully implement multishipping for orders that contain both physical and virtual products. <!--- MC-33818-->

-  {:.fix} Merchants can now create company users from the Company Users section in My Account and Company Structure pages in deployments where **Access Restriction** is enabled and **Restriction Mode** is set to **Sales: Login Only**. Previously, Magento threw this error when a merchant tried to create a user: Can not register new customer due to restrictions are enabled. <!--- MC-33608-->

-  {:.fix} Magento no longer resets a customer’s customer group to the default when a customer saves their account information. <!--- MC-33554-->

-  {:.fix} Magento no longer throws a fatal error when an administrator assigns a customer who has an active shopping cart to a customer group. <!--- MC-33313-->

-  {:.fix} Magento now provides an `addToCart` DataLayer event for Quick Order and Requisition lists pages.  <!--- MC-33295-->

-  {:.fix} Notification emails that are sent to sales representatives assigned to a company now include the assigned corporate logo. Previously, the notification email included the default LUMA logo, not the uploaded corporate logo. <!--- MC-33232-->

-  {:.fix} A requisition list now includes all grouped products and quantities that have been added to the list. Previously, when a merchant navigated to a requisition list after adding products to it from a product detail page, Magento displayed this error: `1 product(s) require your attention - Options were updated. Please review available configurations`. <!--- MC-32877-->

## Magento B2B - Version 1.2.0

-  {:.new} [Storefront Order Search](https://github.com/magento/partners-magento2b2b/pull/16) added thanks to contribution by [Marek Mularczyk]( https://github.com/mmularski) from [Divante](https://www.divante.com/) and community members.
-  {:.new} Purchase Orders have been enhanced and rewritten. They are now included by default in {{site.data.var.ee}}.
-  {:.new} Purchase Order Approval Rules have been implemented. These rules allow users to control the Purchase Order workflow by creating purchasing rules for orders.
-  {:.new} Login as Customer is now included by default in {{site.data.var.ee}}. This allows site employees to assist customers by logging in as the customer to see what they see.

-  {:.fix} Attribute aggregations are now working correctly for Layered Navigation with Elasticsearch
-  {:.fix} Search orders by special characters is now working properly.
-  {:.fix} Clicking on the **Clear All** Button now expands all the filters, rather than collapsing them.
-  {:.fix} Product SKU/Name is now included in the Order History search filter summary.
-  {:.fix} Sorting Indicator is now displayed properly in the My Purchase Orders Grid.
-  {:.fix} Now, you can click the Approve, Cancel, Reject, and Purchase Order buttons only once. Previously, you could click the button multiple times.
-  {:.fix} The Purchase Order Approve, Reject, Cancel, and Validate buttons now render correctly on mobile devices.
-  {:.fix} Previously, approving a Purchase Order with a discount that has expired placed the order at the full amount and did not update the Purchase Order total. This now works correctly.
-  {:.fix} A bug was introduced in 2.3.4 where custom extension attributes would not be copied from the Customer Address to the Quote Address. This bug has been fixed.
-  {:.fix} With B2B installed, a SQL error would appear when assigning categories to shared catalogs. This bug has been fixed.
-  {:.fix} Due to an incorrect variable type value, admins could not add configurable products to an order. The option dropdowns would not populate. This feature now works properly.
-  {:.fix} Previously, when editing Category Permissions for the Not Logged In group, an error would occur when saving the changes. This bug has now been fixed.
-  {:.fix} A bug has been fixed that now allows admins to add products to an order that are not in the shared catalog. Previously, an error message would appear when adding an item not in the catalog.
-  {:.fix} Previously, after running the command `php bin/magento indexer:set-dimensions-mode catalog_product_price website` and then trying to create a shared catalog, an error would occur. This bug has been fixed.
-  {:.fix} When adding a new company and assigning the Company Administrator to a non-default website, the wrong site ID was sent, causing an error. This bug has now been fixed.
-  {:.fix} Previously, after a customer was moved to another customer group, adding a product to an order via Quick View would fail with an error. This bug has now been fixed.
-  {:.fix} Previously, when attempting to checkout using the WebAPI with a B2B quote, an incorrect value was sent to the API, causing an error to occur. This bug has been fixed.
-  {:.fix} Previously, when setting a company to "Active" via the API, an error would occur. This bug has now been fixed.
-  {:.fix} Due to an unneeded `form` tag, the page would refresh when you press Enter after changing a proposed shipping charge. This has been fixed.
-  {:.fix} Previously, when setting a product display limit on a catalog page and that limit was less than the number of total products, an error occurred. That feature now works as expected.
-  {:.fix} Previously, when changing the admin of a company, the original admin address would be copied to the new admin, giving them two addresses. Now, only the correct address is added.
-  {:.fix} Previously, using the API to save a quote item when backorder is set to "Allowed and Notify Customer" would fail. This API call now works as expected.
-  {:.fix} The Fixed Product Tax is now displayed on the Quotes detail page.
-  {:.fix} Previously, clicking on an attachment in the Comments tab of the My Quotes page would fail to download the file. This behavior now works as expected.

### Known Issues

-  Magento throws an exception during upgrade to B2B 1.2.0 in a multi-website deployment. When `setup:upgrade` runs, this error occurs on the `PurchaseOrder` module: `Module Magento_PurchaseOrder: Unable to apply data patch Magento\PurchaseOrder\Setup\Patch\Data\InitPurchaseOrderSalesSequence for moduleMagento_PurchaseOrder`. **Workaround**: Install the **B2B-716 Add NonTransactionableInterface interface to the InitPurchaseOrderSalesSequence data patch** hotfix, which is now available from the **My Account** > **Downloads** section of `magento.com`.
-  If a discount code expires before a Purchase Order (PO) is approved, the PO continues to display the discounted amount, but once the PO is approved, the order is placed at the non-discounted total. **Workaround**: Install the **B2B-709 Purchase Order Discount patch** hotfix for this issue, which is now available from the **My Account** > **Downloads** section of `magento.com`.
-  If items in a purchase order are out-of-stock, or of insufficient quantity when the purchase order is converted into an actual order, an error will occur. If backorders are enabled, the order will be processed normally.
