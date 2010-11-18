### Lifetime

Part creation policy can be one of the following values:

#### CreationPolicy.Shared

*   A single instance of the associated ComposablePart will be created and shared by all requestors.

#### CreationPolicy.NonShared

*   A new instance of the associated ComposablePart will be created for every requestor.

#### CreationPolicy.Any

*   This is the default CreationPolicy; this allows the CompositionContainer to choose the CreationPolicy for the part given the current context. The CompositionContainer will choose CreationPolicy.Shared by default unless the ComposablePart or the importer requests CreationPolicy.NonShared.

