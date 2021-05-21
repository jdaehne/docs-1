Contextual consent allows the website to obtain the consent of the users on
place. This is used to hide embedded YouTube videos and display a placeholder
with a consent button inside.

This function can be extended with the service setting 'Contextual Consent
Only'. If this setting is activated, the service cannot be directly activated
globally with the 'Accept All' workflow in the consent modal. The service is
still hidden by a placeholder, but a second button is displayed which allows the
user to activate the service globally.

The contextual consent feature cannot be disabled, but the consent placeholder
can be hidden by the following css rule:

```css
div[data-type="placeholder"] {
    display: none;
}
```

### Custom placeholder messages
If you would like to create your own custom placeholder to just create an element like this and set the `data-name` to the specific service:
```html
<div data-type="placeholder" data-name="youtube">
    Your custom message
</div>
```
This will replace the default placeholder with your custom placeholder

### Adding custom button to enable specific service
To provide the user a button to directly enable a specific service can be done like this:
```html
<div data-type="placeholder" data-name="youtube">
    Your custom message
    <a onclick="klaro.getManager().updateConsent('youtube', 1);klaro.getManager().saveAndApplyConsents();return false;">Enable Service</a>
</div>
```
Replace `youtube` with your specific service.
