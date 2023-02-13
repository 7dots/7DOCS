# Nice checkbox

This creates a nicer looking checkbox field in the CMS allowing for a left title, a right title, and description.

```silverstripe
$fldNiceCheckbox = FieldGroup::create(
    CheckboxField::create('NiceCheckbox', 'Turn on?')
);
$fldNiceCheckbox->setTitle('NiceCheckbox');
$fldNiceCheckbox->setDescription('This creates a nicer looking checkbox with a left title, a right title, and a description.');
$fields->addFieldsToTab('Root.NiceCheckbox', [
    $fldNiceCheckbox
]);
```

### Example
![Nice checkbox](./img/nice-checkbox.png)
