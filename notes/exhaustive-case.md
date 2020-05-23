# exhaustive-case

```typescript
import { isOnOrAfter, Status } from './status-helper';

// Use for exhaaustive checks in case statements
const unreachable = (x: never): never =>  { throw new Error(`This should be unreachable! but got ${x}`) }

export const businessInitialTabs = ['myRequests']
export const analystInitialTabs = ['allRequests', 'myAssignments']
export const managerInitialTabs = [ 'assignmentQueue', 'allRequests']

// security tabs are shared by the analyst and the manager
export const optionalSecurityTabsObj = {'saRequest': false, 'scope': false, 'threats': false,'controls': false, 'saResponse': false}

export type OptionalSecurityTab= keyof typeof optionalSecurityTabsObj

export const optionalBusinessTabsObj = {'saRequest': false, 'questions': false}

export type OptionalBusinessTab= keyof typeof optionalBusinessTabsObj

const optionalSecurityTabs = Object.keys(optionalSecurityTabsObj) as OptionalSecurityTab[]

export const isOptionalSecurityTabVisible = (tab: OptionalSecurityTab, status: Status) => {
  switch(tab){
    case 'saRequest':return isOnOrAfter(status, 'ANALYSTSCOPINGSTAGE')
    case 'scope': return isOnOrAfter(status, 'ANALYSTSCOPINGSTAGE')
    case 'threats': return isOnOrAfter(status, 'THREATSANDCONTROLS')
    case 'controls': return isOnOrAfter(status, 'THREATSANDCONTROLS')
    case 'saResponse': return isOnOrAfter(status, 'QUESTIONSANSWERED')
    default: unreachable(tab);
  }
}

export const isOptionalBusinessTabVisible = (tab: OptionalBusinessTab, status: Status) => {

  switch(tab){
    case 'saRequest': return status === 'DRAFT'
    case 'questions': return (status ===  'QUESTIONSPOSED')
    default:  return unreachable(tab)
  }
}

type UserRole = 'Business User' | 'Security Analyst' | 'Security Manager';

const getInitialTabs = (role: UserRole) => {
switch(role){
  case 'Business User': return businessInitialTabs;
  case 'Security Analyst': return analystInitialTabs;
  case 'Security Manager': return managerInitialTabs;
  default: return unreachable(role)
}
}

const getOptionalTabs = () => {

}
// More work to do here

export const getVisibleTabs = (status: Status, role: UserRole) => {
  const initTabs = getInitialTabs(role)
  // const optionalTabs = role === 'Business User' ?

}

export const getLastTabIndex = (status: Status, role: UserRole) => {
  // const optionalTabCount = optionalSecurityTabs.map((tab) => {return role === 'Business User' ? isOptionalBusinessTabVisible(tab, status): isOptionalSecurityTabVisible(tab, status) ? tab : undefined}).filter(tab => tab !== undefined).length
  // return getInitialTabs(role).length + optionalTabCount -1
}








```
