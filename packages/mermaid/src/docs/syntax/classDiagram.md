classDiagram
    class Person {
        -personID: String
        -name: String
        +assignToGroup()
    }

    class Group {
        -groupID: String
        -name: String
        +addMember()
        +removeMember()
    }

    class Door {
        -doorID: String
        -location: String
        +assignToGroup()
    }

    class PersonGroup {
        -isPersonGroup: Boolean
    }

    class DoorGroup {
        -isDoorGroup: Boolean
    }

    class AccessRight {
        -rightsID: String
        -timeConstraints: String
        +grantAccess()
        +revokeAccess()
    }

    class SampleWeek {
        -weekID: String
        -description: String
        +applyChanges()
    }

    class Calendar {
        -calendarID: String
        +generate()
        +update()
    }

    Person "1" *-- "0..*" Group : belongs to
    Group <|-- PersonGroup
    Group <|-- DoorGroup
    Door "1" -- "1" DoorGroup : member of
    AccessRight -- PersonGroup : for
    AccessRight -- DoorGroup : grants access to
    Calendar "1" -- "1..*" SampleWeek : contains
