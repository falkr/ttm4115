# Tips for Diagrams



# Have a Strategic Layout


The layout determines where you place your elements in the diagram.
This is an opportunity to convey extra information to the reader and emphasize structural elements in the diagram that go beyond how the graph is connected. 

The figure below shows a deployment diagram where the strategy is to place the nodes not only dependent to their graph strcuture, but also to their hierarchy in the system. Devices running in the cloud are shown at the top and devices running as endpoints (like small devices) are shown in the lowest layer. This already conveys some form of order to the diagram. 

---
type: figure
source: figures/diagrams/deployment-tiers.png
caption: "Layout that follows the system hierarchy."
---


Another example is shown below that follows an entirely different strategy. 
Here the shared communication medium is highlighted, and components are arranged alongside this shared bus.


---
type: figure
source: figures/diagrams/deployment-bus.png
caption: "Layout that emphasizes the communication bus."
---

For state machines, experiment with the arrangement of states. Usually it is easiert for the reader to get a good sense of orientation if you begin with the initial state in the upper left corner, like in a written document.




# Use PDF or PNG


When you create a digram, try to export it in PDF format from the graphical tool.
As a tool for the final report you will most likely use Microsoft Word, which has the option to import PDF graphics.
This has the benefit that the graphic is exported in a vectorized format, and not in a pixeled version. 
If PDF is not available, choose PNG with a resolution that is high enough. That is a pixeled image, but does not use the same compression as JPEG.


---
type: figure
source: figures/diagrams/conversion.png
caption: "Prefer PDF as conversion fromat when importing diagrams into Word to avoid blurred diagrams."
---