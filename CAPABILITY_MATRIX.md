# Capability Matrix

| Capability | State | Evidence level | Boundary |
|---|---|---|---|
| Identify page title, URL, structure, and access state | Verified | Repeated real-page use | Does not imply access to restricted content |
| Capture overlapping long-page screenshots | Observation | Representative virtualized-page use | Viewport and browser behavior vary |
| Merge virtualized content by stable IDs | Observation | Representative long-document use | Pages without stable IDs require lower-confidence fallbacks |
| Structured capture from an authorized page object | Observation | Representative document-object use | Must not export unrelated application state or authentication storage |
| Generate readable Markdown | Observation | Representative text, image, and table content | Complex layouts may require embedded HTML or an explicit downgrade |
| Generate offline HTML | Observation | Representative `file://` browser checks | Fonts, protected media, audio, video, and special embeds may require separate handling |
| Close locally referenced image resources | Observation | Representative image-heavy documents | Does not imply all protected attachments can be downloaded |
| Validate structure, resources, and browser rendering | Observation | Static and browser acceptance checks | A validator must use an independent manifest baseline |
| Handle pagination and multiple collapsible regions | Unverified | No general regression suite | Must be verified per target before claiming completion |

