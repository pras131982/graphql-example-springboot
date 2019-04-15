# graphql-example-springboot

subscription{
listenNewAccount{
  accountNumber
  accountName
}
}


subscription{
  listenNewTransaction{
    transactionId
    transactionDate
    merchantName
  }
}


###########################################################

mutation{
  addAccount(account:{
    accountNumber: 1003
    accountName: "Test Account3"
    accountType: "Credit"
    accountBalance: 5000
  }){
    accountNumber
    accountBalance
  }
}

mutation{
  addCustomer(
    customer:{
      customerId: 1002
      firstName: "TestFirst"
      lastName: "TestLast"
      customerType: "Primary"
      address:{
        addressLine1: "1800 E Spring"
        addressLine2: "Apt 327"
        city: "Plano"
        state: "TX"
        zipCode: 75074
        country: "US"
      }   
    }
  ){
    customerId
    firstName
  }
}


mutation{
  addTransaction(transaction:{
    transactionId: 102
    accountNumber: 1002
    transactionDate: "12/12/2019"
    transactionDescription: "Mobile"
    merchantName: "Best Buy"
  }){
    accountNumber
    transactionId
  }
}


###########################################################

query{
  getAccounts{
    accountName
    accountNumber
    customer{
			firstName
      lastName
      customerType
      address{
        city
        state
        country
      }
    }
    transaction{
      transactionId
      transactionDate
      transactionDescription
      merchantName
    }
  }
}


