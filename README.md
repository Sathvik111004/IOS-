# IOS-
IOS APP DEVELOPER 

import SwiftUI

struct ContentView: View {
    @State private var message = "Hello, World!"
    
    var body: some View {
        NavigationView {
            VStack {
                Text(message)
                    .padding()
                
                Button(action: {
                    message = "WELCOME"
                }) {
                    Text("Tap")
                        .padding()
                        .background(Color.blue)
                        .foregroundColor(.white)
                        .cornerRadius(8)
                }
                
                NavigationLink(destination: ListView()) {
                    Text("List View")
                        .padding()
                        .background(Color.green)
                        .foregroundColor(.white)
                        .cornerRadius(8)
                }
                
                NavigationLink(destination: SecondView()) {
                    Text("Second View")
                        .padding()
                        .background(Color.red)
                        .foregroundColor(.white)
                        .cornerRadius(8)
                }
            }
            .navigationTitle("Home")
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

import SwiftUI

struct ListView: View {
    let items = ["List 1", "List 2", "List 3", "List 4", "List 5"]
    
    var body: some View {
        List(items, id: \.self) { item in
            Text(item)
        }
        .navigationTitle("List View")
    }
}

struct ListView_Previews: PreviewProvider {
    static var previews: some View {
        ListView()
    }
}
import SwiftUI

struct SecondView: View {
    var body: some View {
        VStack {
            Text("This is the second view")
                .padding()
        }
        .navigationTitle("Second View")
    }
}

struct SecondView_Previews: PreviewProvider {
    static var previews: some View {
        SecondView()
    }
}
