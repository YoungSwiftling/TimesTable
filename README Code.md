# TimesTable

//
//  ViewController.swift
//  TimesTableApp
//
//  Created by Alex Ngounou on 8/28/15.
//  Copyright (c) 2015 Syk Syllables. All rights reserved.
//

import UIKit

class ViewController: UIViewController, UITableViewDelegate {
    
    @IBAction func sliderMoved(sender: AnyObject) {
        
        tableView.reloadData() // reloadData runs through numberOfRowsInSection && cellForRowAtIndexPath again and refreshes the TableView with new data from the slider.
        
    }
    
    
    @IBOutlet weak var sliderValue: UISlider!
    @IBOutlet weak var tableView: UITableView!
    

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }
    
    
    
    func tableView(tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        
        return 20   // returns number of cells. We will use the cell numbers to divide by the sliderValue in order to get the times table.
        
        }
    
 
    
    
    func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell {
        
        let cell = UITableViewCell(style: UITableViewCellStyle.Default, reuseIdentifier: "Cell")

        let timesTable = Int(sliderValue.value * 20)
        
        cell.textLabel?.text = String(timesTable * (indexPath.row + 1))
        
        return cell
        
    }

    

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }


}

